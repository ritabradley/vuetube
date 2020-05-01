<template>
    <div
        v-if="videos.length > 0"
        class=" w-full lg:w-1/2 xl:w-1/3 border border-gray-400 rounded-lg mx-auto lg:mx-4 mt-4 lg:mt-0"
    >
        <ul class="list-outside flex flex-col">
            <VideoListItem
                v-for="video in videos"
                v-bind:key="video.etag"
                :video="video"
                @selectVideo="onVideoSelect"
            ></VideoListItem>
        </ul>
    </div>
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
