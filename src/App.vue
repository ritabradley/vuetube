<template>
    <div class="w-5/6 lg:w-full mx-auto lg:flex flex-col">
        <h1 class="text-4xl lg:text-5xl text-center font-logo mt-8"><i class="fab fa-youtube pr-2"></i>VueTube</h1>
        <SearchBar @termChange="onTermChange"></SearchBar>
        <div class="lg:flex">
            <VideoDetail :video="selectedVideo"></VideoDetail>
            <VideoList @selectVideo="onVideoSelect" :videos="videos"></VideoList>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './components/SearchBar';
    import VideoDetail from './components/VideoDetail';
    import VideoList from './components/VideoList';
    const API_KEY = 'AIzaSyDMS74EgWqhSl9cKZ0Ktv7YTojXrlhtYF0';

    export default {
        name: 'App',
        components: {
            SearchBar,
            VideoDetail,
            VideoList,
        },
        data() {
            return {
                videos: [],
                selectedVideo: null,
            };
        },
        methods: {
            onTermChange(searchTerm) {
                axios
                    .get('https://www.googleapis.com/youtube/v3/search', {
                        params: {
                            key: API_KEY,
                            type: 'video',
                            part: 'snippet',
                            q: searchTerm,
                        },
                    })
                    .then((res) => (this.videos = res.data.items));
            },
            onVideoSelect(video) {
                this.selectedVideo = video;
            },
        },
    };
</script>

<style></style>
