<template>
    <ul class="list-outside flex flex-col w-1/3 border border-gray-400 rounded-lg divide-y divide-gray-400 mx-4">
        <VideoListItem
            v-for="video in videos"
            v-bind:key="video.etag"
            :video="video"
            @selectVideo="onVideoSelect"
        ></VideoListItem>
    </ul>
</template>

<script>
    import VideoListItem from './VideoListItem';
    export default {
        name: 'VideoList',
        props: {
            videos: Array,
        },
        methods: {
            onVideoSelect(video) {
                this.$emit('selectVideo', video);
            },
        },
        components: {
            VideoListItem,
        },
    };
</script>

<style></style>
