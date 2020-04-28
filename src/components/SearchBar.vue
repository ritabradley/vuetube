<template>
    <div>
        <input class="border border-gray-400 shadow outline-none rounded-sm" type="search" @input="onInput" />
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
    };
</script>

<style></style>
