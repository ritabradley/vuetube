<template>
    <div class="flex justify-center my-10">
        <input
            class="border border-gray-400 shadow outline-none rounded-md w-3/4 p-2"
            type="search"
            :placeholder="placeholder"
            @input="onInput"
        />
    </div>
</template>

<script>
    export default {
        name: 'SearchBar',
        methods: {
            onInput(e) {
                this.$emit('termChange', e.target.value);
            },
        },
        data() {
            return {
                placeholder: 'Search for videos',
            };
        },
    };
</script>

<style></style>
