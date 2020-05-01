<template>
    <div v-if="video" class="w-2/3 mx-4 text-center">
        <div class="border border-black bg-white text-gray-900 rounded-b-md p-6 shadow-xl">
            <h2 class="font-bold text-2xl mb-2">{{ title }}</h2>
            <p class="px-10">{{ description }}</p>
        </div>
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
