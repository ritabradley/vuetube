<template>
    <div class="w-2/3 px-10 text-center">
        <h2 class="font-bold text-2xl mb-2">{{ title }}</h2>
        <p>{{ description }}</p>
    </div>
</template>

<script>
    export default {
        name: 'VideoDetail',
        props: {
            video: Object,
        },
        computed: {
            title() {
                return this.video.snippet.title;
            },
            description() {
                return this.video.snippet.description;
            },
        },
    };
</script>

<style></style>
