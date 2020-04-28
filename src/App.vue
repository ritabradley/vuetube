<template>
    <div>
        <SearchBar @termChange="onTermChange"></SearchBar>
        <VideoList></VideoList>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './components/SearchBar';
    import VideoList from './components/VideoList';
    const API_KEY = 'AIzaSyDMS74EgWqhSl9cKZ0Ktv7YTojXrlhtYF0';

    export default {
        name: 'App',
        props: {},
        components: {
            SearchBar,
            VideoList,
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
                    .then((res) => console.log(res));
            },
        },
    };
</script>

<style></style>
