<template>

    <div class="category_list" >
        <CategoryItem @selected="select" :selected="selected" :item="category" v-for="category in categories"></CategoryItem>
    </div>

</template>

<script>
import CategoryItem from './CategoryItem.vue';
    export default {
    name: "CategoryList",
    props: {
        selected: Number,
        categories: Array
    },
    components: { CategoryItem },
    methods: {
        select(id) {
            this.$emit('selected', id)
        }
    }
}
</script>

<style scoped>

.category_list {
    display: flex;
}

</style>