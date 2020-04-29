<template>
    <li class="flex border border-gray-500 rounded-lg">
        <img class="m-2" :src="video.snippet.thumbnails.default.url" :alt="video.snippet.description" />
        <span class="text-xl font-bold">{{ video.snippet.title }}</span>
    </li>
</template>

<script>
    export default {
        name: 'VideoListItem',
        props: {
            video: Object,
        },
    };
</script>

<style></style>
