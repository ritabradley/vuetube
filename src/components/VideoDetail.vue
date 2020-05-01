<template>
    <div v-if="video" class="w-full lg:w-1/2 xl:w-2/3 mx-auto lg:mx-4 text-center">
        <iframe
            class="w-full h-full"
            :src="videoUrl"
            frameborder="0"
            allow="accelerometer; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
        ></iframe>
        <div class="border border-gray-700 bg-white text-gray-900 rounded-b-md p-6 shadow-xl">
            <h2 class="font-bold text-lg lg:text-2xl mb-2">{{ title }}</h2>
            <p class="px-6 lg:px-10">{{ description }}</p>
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
            videoUrl() {
                const { videoId } = this.video.id;
                return `https://www.youtube.com/embed/${videoId}`;
            },
        },
    };
</script>
