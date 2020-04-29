<template>
    <ul class="list-outside flex flex-col w-1/3">
        <VideoListItem v-for="video in videos" v-bind:key="video.etag" :video="video"></VideoListItem>
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
