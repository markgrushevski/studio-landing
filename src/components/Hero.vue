<script setup></script>

<template>
    <div class="hero">
        <div class="hero__filter"></div>

        <div class="hero__content color-white">
            <nav class="hero__navbar font-header">
                <a href="/">Главная</a>
                <a href="#about">О нас</a>
                <a href="#service">Услуги</a>
                <a href="#reviews">Отзывы</a>
                <a href="#projects">Наши проекты</a>
                <a href="#contacts">Контакты</a>
            </nav>

            <div class="hero__headline">
                <h1>
                    Студия дизайна <br />интерьера <br /><span class="color-accent">Ксении <br />Филатовой</span>
                </h1>
                <h3>Делаем ваше пространство <br />стильным, удобным <br />и функциональным.</h3>
                <button class="bg-accent rounded">Посмотреть услуги</button>
            </div>
        </div>
    </div>
</template>

<style>
.hero {
    width: 1024px;
    height: 768px;

    position: relative;

    background-image: url(/main.png);
    background-repeat: no-repeat;
}

.hero__filter {
    position: absolute;
    z-index: 1;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #22222266;
}

.hero__content {
    position: absolute;
    z-index: 2;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.hero__navbar {
    margin-top: 30px;

    height: 13px;

    display: flex;
    align-items: center;
    justify-content: center;
    gap: 40px;
}

.hero__headline {
    margin-top: 70px;
    margin-left: 442px;
}

.hero__headline h3 {
    margin: 20px 0 40px;
}

.hero__headline button {
    width: 220px;
    height: 50px;
}
</style>
