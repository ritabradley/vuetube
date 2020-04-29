<template>
    <li class="flex p-4 cursor-pointer">
        <img class="m-2" :src="thumbnail" :alt="description" />
        <span class="text-xl font-bold self-center">{{ title }}</span>
    </li>
</template>

<script>
    export default {
        name: 'VideoListItem',
        props: {
            video: Object,
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
