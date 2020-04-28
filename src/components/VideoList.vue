<template>
    <ul class="list-outside">
        <VideoListItem v-for="video in videos" v-bind:key="video.id.videoId">{{ video }}</VideoListItem>
    </ul>
</template>

<script>
    import VideoListItem from './VideoListItem';
    export default {
        name: 'VideoList',
        props: {
            videos: Array,
        },
        components: {
            VideoListItem,
        },
    };
</script>

<style></style>
