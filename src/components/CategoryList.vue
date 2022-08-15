<template>

    <div class="category_list" >
        <CategoryItem @selected="select" :selected="selected" :item="category" v-for="category in categories"></CategoryItem>
    </div>

</template>

<script>
import CategoryItem from './CategoryItem.vue';
    export default {
    name: "CategoryList",
    data() {
        return {
            selected: 0,
            categories: [
                {   
                    id: 0,
                    title: "Все",
                    image: "https://www.clipartmax.com/png/full/246-2463530_hamburger-cheeseburger-fast-food-veggie-burger-junk-cartoon.png"
                },
                {
                    id: 1,
                    title: "Бургеры",
                    image: "https://www.clipartkey.com/mpngs/b/10-102666_hamburger-clipart.png"
                },
                {
                    id: 2,
                    title: "Десерты",
                    image: "https://www.vippng.com/png/full/517-5177715_quotes-vector-dessert-ice-cream-and-cake-clipart.png"
                },
                {
                    id: 3,
                    title: "Напитки",
                    image: "https://www.vippng.com/png/full/441-4411545_coca-cola-soft-drink-carbonated-drink-pepsi-coca.png"
                }
            ]
        };
    },
    components: { CategoryItem },
    methods: {
        select(id) {
            this.selected = id
        }
    }
}
</script>

<style scoped>

.category_list {
    display: flex;
}

</style>