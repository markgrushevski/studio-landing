<script setup>
import { ref } from 'vue';

const showModal = ref(false);

function openModal() {
    showModal.value = true;

    setTimeout(() => {
        showModal.value = false;
    }, 1750);
}
</script>

<template>
    <div class="callback">
        <img src="/12.png" alt="" />
        <div class="callback__content">
            <h2>Хотите узнать больше о наших услугах?</h2>
            <header>Заполните форму, и мы перезвоним вам <br />в ближайшее время для консультации.</header>
            <form class="font-text" @submit.prevent>
                <input placeholder="Имя" type="text" />
                <input placeholder="Номер телефона" type="tel" />
                <label class="font-text-small"
                    ><input type="checkbox" />Соглашаюсь на обработку персональных данных</label
                >
                <button class="bg-accent rounded color-white" @click="openModal">Заказать звонок</button>
            </form>
        </div>

        <h3 :class="{ ['callback__modal_active']: showModal }" class="callback__modal bg-white">
            Спасибо! <br />Мы свяжемся с вами <br />в течение дня.
        </h3>
    </div>
</template>

<style>
.callback {
    display: flex;
    align-items: center;
    gap: 20px;
}

.callback__content {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.callback__content > form {
    width: 372px;

    display: flex;
    flex-direction: column;
    gap: 30px;
}

.callback__content > form > input {
    width: 100%;
    height: 26px;

    border-bottom: 1px solid var(--color-black);
}

.callback__content > form > label {
    width: 100%;
    height: 20px;

    display: flex;
    gap: 9px;
}

.callback__content > form > label > input {
    width: 18px;
    height: 18px;
}

.callback__content > form > button {
    margin-top: 10px;

    width: 220px;
    height: 50px;
}

.callback__modal {
    position: fixed;
    top: calc(50vh - (330px / 2));
    left: calc(50vw - (530px / 2));

    display: flex;
    align-items: center;
    justify-content: center;

    width: 530px;
    height: 330px;

    text-align: center;

    transition: opacity ease-out 0.1s;

    opacity: 0;
    pointer-events: none;
}

.callback__modal.callback__modal_active {
    opacity: 1;
    pointer-events: auto;
    box-shadow: rgba(99, 99, 99, 0.2) 0 2px 8px 0;
}
</style>
