import WelcomeMessage from '@/components/WelcomeMessage.vue';

<template>
    <div class="about-ve">
        <h1>{{ pageName }}</h1>
        <p>{{ pageDescription }}</p>
    </div>
</template>

<script>
// @ is an alias to /src

export default {
    data: function () {
        return {
            pageName: "About Us",
            pageDescription: "This Is About Us Page",
        };
    },
    name: "about-ve",
};
</script>
