<template>
    <div>
        <h2>Вкусная еда</h2>
        <div class="food_list">
            <FoodItem v-for="item in filteredFood" :item="item"></FoodItem>
        </div>
    </div>
</template>
<script>
import FoodItem from "./FoodItem.vue";
export default {
    name: "FoodList",
    props: {
        selected: Number
    },
    data() {
        return {
            filteredFood: [],
            food: [
                {
                    id: 1,
                    title: "Кантри",
                    category_id: 1,
                    desc: "froewvbneo fjjorr j3rioh wh nerio",
                    price: 4,
                    selected: false,
                    image: 'https://www.burgerking.ee/images/optimized/products/crispy-chicken-desktop-c4bfa6675291eb3d02d0b63bebfe7473.png'
                },
                {
                    id: 2,
                    title: "Наполеон",
                    category_id: 2,
                    desc: "Food Delivery service - App Design designed ",
                    price: 2,
                    selected: false,
                    image: 'https://darpizza.com/image/cache/catalog/products/deserti/napaleon-500x500.png'
                },
                {
                    id: 3,
                    title: "БигМак",
                    category_id: 1,
                    desc: "Учет бюджета не прошел даром",
                    price: 5,
                    selected: false,
                    image: 'https://bonfit.ru/upload/iblock/60f/60fcdc5b141e233dc2eb354589a699ca.png'
                },
                {
                    id: 4,
                    title: "Кока-кола",
                    category_id: 3,
                    desc: "Праздник к нам приходит",
                    price: 1,
                    selected: false,
                    image: 'https://purepng.com/public/uploads/large/purepng.com-coca-colacoca-colacokecarbonated-soft-drinksoft-drink-141152723341416a62.png'
                },
            ]
        };
    },
    watch: {
        selected(newSelected, oldSelected) {

            if (newSelected == 0) {
                this.filteredFood = this.food
            } else {
                this.filteredFood = this.food.filter(item => item.category_id == newSelected)
            }


        }
    },
    mounted(){
        this.filteredFood = this.food
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
</style>