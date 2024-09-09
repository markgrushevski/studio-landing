<script setup>
import { computed, ref, useTemplateRef, watch } from 'vue';

const reviews = [
    {
        id: 1,
        title: 'Дизайн офиса',
        size: '363 m²',
        author: {
            name: 'Иван Марков',
            age: '28',
            job: 'Предприниматель',
            photo: '/5.png'
        },
        text: 'Как принято считать, тщательные исследования конкурентов представляют собой не что иное, как квинтэссенцию победы маркетинга над разумом и должны быть указаны как претенденты на роль ключевых.'
    },
    {
        id: 2,
        title: 'Дизайн квартиры',
        size: '67 m²',
        author: {
            name: 'Елена Кузнецова',
            age: '32',
            job: 'Дизайнер одежды',
            photo: '/6.png'
        },
        text: 'Принимая во внимание показатели успешности, реализация намеченных плановых заданий требует анализа новых предложений. Учитывая ключевые сценарии поведения, граница обучения кадров способствует.'
    },
    {
        id: 3,
        title: 'Дизайн винного бара',
        size: '380 m²',
        author: {
            name: 'Софья Волкова',
            age: '30',
            job: 'Менеджер по продажам',
            photo: '/7.png'
        },
        text: 'Не следует, однако, забывать, что курс на социально-ориентированный национальный проект является качественно новой ступенью прогресса профессионального сообщества. Разнообразный и богатый опыт.'
    },
    {
        id: 4,
        title: 'Дизайн офиса',
        size: '363 m²',
        author: {
            name: 'Иван Марков',
            age: '28',
            job: 'Предприниматель',
            photo: '/5.png'
        },
        text: 'Как принято считать, тщательные исследования конкурентов представляют собой не что иное, как квинтэссенцию победы маркетинга над разумом и должны быть указаны как претенденты на роль ключевых.'
    },
    {
        id: 5,
        title: 'Дизайн квартиры',
        size: '67 m²',
        author: {
            name: 'Елена Кузнецова',
            age: '32',
            job: 'Дизайнер одежды',
            photo: '/6.png'
        },
        text: 'Принимая во внимание показатели успешности, реализация намеченных плановых заданий требует анализа новых предложений. Учитывая ключевые сценарии поведения, граница обучения кадров способствует.'
    }
];

const getStartIndexes = () => [0, 1, 2];
const getReversedStartIndexes = () => [reviews.length - 3, reviews.length - 2, reviews.length - 1];

const cards = useTemplateRef('cards');
const currentReviews = ref(getStartIndexes());

const scrollValue = computed(() => cards.value?.firstElementChild?.scrollWidth + 20 || 0);

function scrollRight(ev) {
    if (cards.value) {
        cards.value.scrollBy(scrollValue.value, 0);

        const maxI = reviews.length - 1;
        const currentLastI = currentReviews.value.at(-1);

        if (currentLastI === maxI) {
            currentReviews.value = getStartIndexes();
            cards.value.scrollTo(0, 0);
        } else if (currentLastI < maxI) {
            currentReviews.value.push(currentLastI + 1);
            currentReviews.value.shift();
        }
    }
}

function scrollLeft(ev) {
    if (cards.value) {
        cards.value.scrollBy(-scrollValue.value, 0);

        const lastStartI = getStartIndexes().at(-1);
        const currentLastI = currentReviews.value.at(-1);

        if (currentLastI === lastStartI) {
            currentReviews.value = getReversedStartIndexes();
            cards.value.scrollTo(cards.value.scrollWidth, 0);
        } else if (currentLastI > lastStartI) {
            currentReviews.value.unshift(currentLastI - getStartIndexes().length);
            currentReviews.value.pop();
        }
    }
}
</script>

<template>
    <div id="review" class="review">
        <h2 class="bold">Отзывы клиентов</h2>

        <div class="review__cards" ref="cards">
            <div v-for="review in reviews" :key="review.id" class="review__card">
                <div class="review__title font-text">
                    <span>{{ review.title }}</span>
                    <span>{{ review.size }}</span>
                </div>
                <div class="review__author">
                    <img :src="review.author.photo" alt="" />
                    <div>
                        <header>{{ review.author.name }}, {{ review.author.age }}</header>
                        <div class="font-text-small">{{ review.author.job }}</div>
                    </div>
                </div>
                <div class="font-text-small">{{ review.text }}</div>
            </div>
        </div>

        <div class="review__controls">
            <div class="review__dots">
                <div
                    v-for="(review, i) in reviews"
                    :key="review.id"
                    :class="currentReviews.includes(i) ? 'bg-secondary-active' : 'bg-secondary'"
                    class="review__dot"
                ></div>
            </div>

            <div class="review__arrows">
                <div class="border border-secondary color-secondary bg-white" @click="scrollLeft">
                    <svg
                        fill="currentColor"
                        width="11"
                        height="8"
                        viewBox="0 0 11 8"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M0.646446 4.35355C0.451184 4.15829 0.451184 3.84171 0.646446 3.64645L3.82843 0.464466C4.02369 0.269204 4.34027 0.269204 4.53553 0.464466C4.7308 0.659728 4.7308 0.976311 4.53553 1.17157L1.70711 4L4.53553 6.82843C4.7308 7.02369 4.7308 7.34027 4.53553 7.53553C4.34027 7.7308 4.02369 7.7308 3.82843 7.53553L0.646446 4.35355ZM1 3.5H11V4.5H1V3.5Z"
                        />
                    </svg>
                </div>
                <div class="border border-secondary color-secondary bg-white" @click="scrollRight">
                    <svg
                        fill="currentColor"
                        width="11"
                        height="8"
                        viewBox="0 0 11 8"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M10.3536 4.35355C10.5488 4.15829 10.5488 3.84171 10.3536 3.64645L7.17157 0.464466C6.97631 0.269204 6.65973 0.269204 6.46447 0.464466C6.2692 0.659728 6.2692 0.976311 6.46447 1.17157L9.29289 4L6.46447 6.82843C6.2692 7.02369 6.2692 7.34027 6.46447 7.53553C6.65973 7.7308 6.97631 7.7308 7.17157 7.53553L10.3536 4.35355ZM10 3.5H0V4.5H10V3.5Z"
                        />
                    </svg>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.review {
}

.review__cards {
    margin-top: 40px;

    display: flex;
    gap: 20px;

    overflow-x: auto;

    scrollbar-width: none;
    scroll-behavior: smooth;
}

.review__card {
    display: flex;
    flex-direction: column;
    gap: 20px;

    min-width: 300px;
}

.review__title {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid;
}

.review__author {
    margin-top: 20px;

    display: flex;
    align-items: center;
    gap: 20px;
}

.review__controls {
    margin-top: 52px;

    position: relative;

    display: flex;
    align-items: center;
    justify-content: center;
}

.review__dots {
    display: inline-flex;
    align-items: center;
    gap: 8px;
}

.review__dot {
    width: 5px;
    height: 5px;
}

.review__arrows {
    position: absolute;
    right: 0;

    display: inline-flex;
    align-items: center;
    gap: 14px;
}

.review__arrows > * {
    width: 30px;
    height: 30px;

    display: flex;
    align-items: center;
    justify-content: center;
}

.review__arrows > *:hover,
.review__arrows > *:active {
    border-color: var(--color-secondary-active);
    color: var(--color-secondary-active);
}
</style>
