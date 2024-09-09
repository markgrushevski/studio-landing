<script setup>
import Footer from './Footer.vue';
import Info from './Info.vue';
import Callback from './Callback.vue';
</script>

<template>
    <div id="contacts">
        <Callback />
        <Info />
        <Footer />
    </div>
</template>

<style>
#contacts {
    display: flex;
    flex-direction: column;
    gap: 120px;
}
</style>
