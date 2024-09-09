<script setup>
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Service from './components/Service.vue';
import Review from './components/Review.vue';
import Projects from './components/Projects.vue';
import Contacts from './components/Contacts/Contacts.vue';
</script>

<template>
    <!--<div
        style="
            padding: 0;
            position: fixed;
            top: 0;
            left: calc(50% - 1px);
            height: 100vh;
            z-index: 10;
            border: 2px solid #646464;
            transform: translateX(-512px);
        "
    ></div>
    <div
        style="
            padding: 0;
            position: fixed;
            top: 0;
            left: calc(50% - 1px);
            height: 100vh;
            z-index: 10;
            border: 2px solid #646464;
        "
    ></div>
    <div
        style="
            padding: 0;
            position: fixed;
            top: 0;
            left: calc(50% - 1px);
            height: 100vh;
            z-index: 10;
            border: 2px solid #646464;

            transform: translateX(512px);
        "
    ></div>-->

    <Hero />
    <About />
    <Service />
    <Review />
    <Projects />
    <Contacts />
</template>

<style>
#app {
    margin: 0 auto;

    max-width: 1024px;

    position: relative;

    display: flex;
    flex-direction: column;
    gap: 120px;

    overflow: hidden;
}

#app > * {
    padding: 0 42px;
}
</style>
