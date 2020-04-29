<template>
    <div>
        <h1 class="text-5xl text-center font-logo mt-8"><i class="fab fa-youtube pr-2"></i>VueTube</h1>
        <SearchBar @termChange="onTermChange"></SearchBar>
        <VideoList :videos="videos"></VideoList>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './components/SearchBar';
    import VideoList from './components/VideoList';
    const API_KEY = 'AIzaSyDMS74EgWqhSl9cKZ0Ktv7YTojXrlhtYF0';

    export default {
        name: 'App',
        components: {
            SearchBar,
            VideoList,
        },
        data() {
            return {
                videos: [],
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
        },
    };
</script>

<style></style>
