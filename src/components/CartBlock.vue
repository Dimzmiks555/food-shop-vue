<template>
    <div class="cart_block">
        <div class="cart_item" v-for="item in cartProducts">
            <div>
                <img :src="item.image">
            </div>
            <h3>{{item.title}}</h3>
            <span>${{item.price}}</span>
        </div>
        <div v-if="cartProducts.length > 0" class="cart_footer">
            <h2>Итого <b>${{getTotalSumm}}</b></h2>
            <button>
                Купить
            </button>
        </div>
        <div v-else>
            <h2>Корзина пуста</h2>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            cartProducts: []
        }
    },
    props: {
        food: Array,
        cart: Array
    },
    computed: {
        getTotalSumm() {
            return this.cartProducts.reduce((prev, now) => prev + now?.price, 0)
        }
    },
    mounted(){
        this.cartProducts = this.food.filter(item => this.cart.includes(item.id))
    },
    watch: {
        cart: {
            deep: true,
            handler(newCart, oldCart){
                console.log(newCart, oldCart)
                this.cartProducts = this.food.filter(item => newCart.includes(item.id))
            }
        }
    }

}
</script>
<style scoped>
    .cart_block {
        margin-top: 40px;
    }
    .cart_item {
        display: flex;
        align-items: center;
        border: 2px solid #ddd;
        border-radius: 20px;
        padding: 10px 30px;
        margin-bottom: 20px;
    }
    .cart_item img {
        width: 80px;
        height: 80px;
        object-fit: scale-down;
        margin-right: 20px;
    }
    .cart_item h2 {
        width: 100%;
        /* margin-top: 10px; */
    }
    .cart_item span {
        margin-left: auto;
        font-size: 20px;
        font-weight: 900;
    }
    .cart_footer button {
        width: 100%;
        background: #234;
        color: #fff;
        font-family: inherit;
        padding: 20px 30px;
        border-radius: 20px;
        font-size: 20px;
        cursor: pointer;
    }
    .cart_footer button:hover {
        background: #456;
    }
    .cart_footer b {
        margin-left: auto;
    }
</style>