<template>
    <div class="search">
        <input @input="searchFood" :value="search" placeholder="Поиск...">
    </div>
</template>
<script>
export default {
    props: {
        search: String
    },
    methods: {
        searchFood(e) {
            console.log(e.target.value)
            this.$emit('searched', e.target.value)
        }
    }
}
</script>
<style scoped>
    .search input {
        height: 60px;
        padding: 10px 20px;
        border: 1px solid #ccc;
        border-radius: 16px;
        font-size: 16px;
        font-family: inherit;
    }
</style>