<script setup>
import { computed, ref } from 'vue';

const designs = [
    {
        id: 1,
        name: 'Дизайн №1',
        title: 'Базовый',
        description:
            'Для тех, кто хочет побыстрее приступить \nк реализации. \n\nБазовый набор услуг для быстрого старта \nдизайн-проекта по отличной цене.',
        image: '/2.png'
    },
    {
        id: 2,
        name: 'Дизайн №2',
        title: 'Оптимальный',
        description:
            'Золотое соотношение по стоимости и составу работ. Включены 3D-визуализации, список мебели и чистовых материалов. \n\nПодойдет для оформления любой квартиры \nили дома.',
        image: '/3.png'
    },
    {
        id: 3,
        name: 'Дизайн №3',
        title: 'Премиум',
        description:
            '3D-визуализации вашего нового интерьера, 2 ракурса на помещение. В комплектации отдаем предпочтение мебели и отделочным \nэлементам от западных производителей. \n\n1 месяц авторского сопровождения в подарок, включает 3 выезда на объект.',
        image: '/4.png'
    }
];

const selectedDesignId = ref(1);

const currentDesign = computed(() => designs.find((design) => design.id === selectedDesignId.value));

function selectDesign(id) {
    selectedDesignId.value = id;
}
</script>

<template>
    <div id="service" class="service">
        <div class="service__title">
            <h2 class="bold">Пакет услуг</h2>
            <div class="font-text color-secondary-active">
                Финальную цену проекта всегда обсуждаем на встрече в офисе.
            </div>
        </div>

        <div class="service__selectors">
            <div class="service__line border"></div>
            <button
                v-for="design in designs"
                :key="design.id"
                :class="{ ['border-accent']: design.id === selectedDesignId }"
                class="bg-white font-text-large border rounded"
                @click="selectDesign(design.id)"
            >
                {{ design.name }}
            </button>
        </div>

        <div class="service__design">
            <div class="service__description">
                <h3>{{ currentDesign.title }}</h3>
                <span class="font-text">{{ currentDesign.description }}</span>
                <button class="bg-accent color-white rounded">Выбрать дизайн</button>
            </div>
            <div class="service__image">
                <img :src="currentDesign.image" alt="" />
            </div>
        </div>
    </div>
</template>

<style>
.service {
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 40px;

    text-align: center;
}

.service__title {
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 20px;
}

.service__selectors {
    position: relative;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.service__line {
    position: absolute;
    top: 50%;
    width: 100%;
    z-index: -1;
}

.service__selectors > button {
    width: 215px;
    height: 60px;
}

.service__selectors > button:hover,
.service__selectors > button:active {
    border-color: var(--color-accent);
}

.service__design {
    width: 100%;

    display: flex;
    align-items: center;
    justify-content: space-between;
}

.service__description {
    display: flex;
    flex-direction: column;
    gap: 20px;

    text-align: start;
}

.service__description > button {
    margin-top: 20px;
    width: 220px;
    height: 50px;
}

.service__description > span {
    white-space: pre-wrap;
}

.service__image {
}
</style>
