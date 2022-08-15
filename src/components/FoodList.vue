<template>
    <div>
        <h2>Вкусная еда</h2>
        <div class="food_list">
            <FoodItem @deletedFromCart="deleteFromCart" @addedToCart="addToCart" v-for="item in filteredFood" :item="item" :cart="cart"></FoodItem>
        </div>
        <div class="empty" v-if="filteredFood.length == 0">
            <h2>Ничего не найдено 😢</h2>
        </div>
    </div>
</template>
<script>
import FoodItem from "./FoodItem.vue";
export default {
    name: "FoodList",
    props: {
        selected: Number,
        filteredFood: Array,
        cart: Array
    },
    methods: {
        addToCart(id){
            this.$emit('addedToCart', id)
        },
        deleteFromCart(id) {
            this.$emit('deletedFromCart', id)
        }
    },
    components: { FoodItem }
}
</script>
<style scoped>
    .food_list {
        flex-wrap: wrap;
        margin-top: 20px;
        display: flex;
    }
    .empty {
        width: 100%;
        display: flex;
        justify-content: center;
    }
</style>