<script setup></script>

<template>
    <div class="info">
        <div class="info__details">
            <h2 class="bold">Контакты</h2>
            <h3>+7 (495) 485-36-75</h3>
            <div class="font-text">
                <div>Москва, ул. Кузнецкий мост, 3с1 <br />5 минут от метро «Театральная»</div>
                <div class="color-secondary-active">Часы работы: 10:00-22:00</div>
            </div>
            <header>Почта: kseniya-f@design.com</header>
        </div>
        <img src="/map.png" alt="" />
    </div>
</template>

<style>
.info {
    height: 300px;

    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}

.info__details {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.info__details > header {
    margin-bottom: 8px;
}
</style>
