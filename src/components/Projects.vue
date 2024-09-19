<script setup>
const projects = [
    {
        id: 1,
        name: 'Кофейня',
        size: '63 м²',
        style: 'Скандинавский',
        image: '/8.png'
    },
    {
        id: 2,
        name: 'Офис',
        size: '220 м²',
        style: 'Лофт',
        image: '/9.png'
    },
    {
        id: 3,
        name: 'Жилая квартира',
        size: '59 м²',
        style: 'Минимализм',
        image: '/10.png'
    },
    {
        id: 4,
        name: 'Жилая квартира',
        size: '46 м²',
        style: 'Минимализм',
        image: '/11.png'
    }
];
</script>

<template>
    <div id="projects" class="projects">
        <h2 class="bold">Наши проекты</h2>

        <div>
            <div v-for="(project, i) in projects" :key="project.id" class="projects__project color-white">
                <img :src="project.image" alt="" />

                <div class="projects__content">
                    <div class="projects__number font-text">{{ '0' + (i + 1) }}</div>

                    <div class="projects__description">
                        <span class="font-button color-accent">{{ project.name }}</span>
                        <div class="font-text">
                            <span>Квадраты</span>
                            <span>{{ project.size }}</span>
                        </div>
                        <div class="font-text">
                            <span>Стиль</span>
                            <span>{{ project.style }}</span>
                        </div>
                    </div>

                    <svg
                        fill="currentColor"
                        width="62"
                        height="8"
                        viewBox="0 0 62 8"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M60.9919 4.35355C61.1871 4.15829 61.1871 3.84171 60.9919 3.64645L57.8099 0.464466C57.6146 0.269204 57.298 0.269204 57.1028 0.464466C56.9075 0.659728 56.9075 0.976311 57.1028 1.17157L59.9312 4L57.1028 6.82843C56.9075 7.02369 56.9075 7.34027 57.1028 7.53553C57.298 7.7308 57.6146 7.7308 57.8099 7.53553L60.9919 4.35355ZM60.6383 3.5H0.638306V4.5H60.6383V3.5Z"
                        />
                    </svg>
                </div>
            </div>
        </div>

        <button class="font-text-large bg-white border border-accent rounded">Ещё проекты</button>
    </div>
</template>

<style>
.projects {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.projects > h2 {
    text-align: center;
}

.projects > div {
    display: grid;
    grid-template-rows: 1fr 1fr;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

.projects > button {
    margin: 0 auto;

    width: 215px;
    height: 60px;
}

.projects__project {
    position: relative;

    overflow: hidden;
}

.projects__project > img {
    width: 100%;
    height: 100%;

    transition: transform ease-in-out 0.15s;
}

.projects__project:hover > img {
    transform: scale(1.015);
}

.projects__content {
    position: absolute;
    top: 59px;
    left: 29px;
    right: 29px;
    bottom: 71px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.projects__content svg {
    position: absolute;
    right: 0;
    bottom: 0;
}

.projects__number {
    text-align: right;
}

.projects__description {
    width: 300px;

    display: flex;
    flex-direction: column;
    gap: 20px;
}

.projects__description > div {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid var(--color-white);
}
</style>
