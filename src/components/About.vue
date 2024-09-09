<script setup></script>

<template>
    <div id="about" class="about">
        <div class="about__image">
            <img src="/1.png" alt="" />
            <h2>Мы создаем красивые интерьеры, в которых удобно жить.</h2>
        </div>
        <div class="about__text">
            <div class="about__block">
                <h4>Разрабатываем дизайн</h4>
                <div class="border"></div>
                <span class="font-text">
                    Разрабатываем эксклюзивные интерьеры для частных и общественных объектов. Придумываем смелые решения
                    дизайна, которые сочетают стиль и комфорт для проживания.
                </span>
            </div>
            <div class="about__block">
                <h4>Комплектуем интерьеры</h4>
                <div class="border"></div>
                <span class="font-text">
                    У нас есть производство, где мы изготавливаем любую встраиваемую мебель. Это позволяет нам не
                    ограничивать полет фантазии дизайнера на этапе проектирования интерьера. Работаем с международными
                    фабриками.
                </span>
            </div>
            <div class="about__block">
                <h4>Делаем ремонт</h4>
                <div class="border"></div>
                <span class="font-text">
                    Наша бригада рабочих имеет большой опыт работы с современными материалами и без проблем справляется
                    с необычными дизайнерскими решениями.
                </span>
            </div>
        </div>
    </div>
</template>

<style>
.about {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.about__image {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 40px;
}

.about__text {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.about__block {
    display: grid;
    grid-template-columns: 1fr 60px 1fr;
    align-items: center;
    justify-content: center;
    gap: 20px;
}
</style>
