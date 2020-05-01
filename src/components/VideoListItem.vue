<template>
    <li class="flex p-4 cursor-pointer hover:bg-red-600 border-t first:border-t-0" @click="onVideoSelect">
        <img class="m-2" :src="thumbnail" :alt="description" />
        <h3 class="text-md lg:text-xl font-bold self-center">{{ title }}</h3>
    </li>
</template>

<script>
    export default {
        name: 'VideoListItem',
        props: {
            video: Object,
        },
        methods: {
            onVideoSelect() {
                this.$emit('selectVideo', this.video);
            },
        },
        computed: {
            thumbnail() {
                return this.video.snippet.thumbnails.default.url;
            },
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
