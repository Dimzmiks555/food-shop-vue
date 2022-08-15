<template>
    <div class="food_item">
        <img :src="item.image">
        <h3>{{item.title}}</h3>
        <p>{{item.desc}}</p>
        <div class="footer">
            <span>${{item.price}}</span>
            <button v-if="!cart.includes(item.id)" @click="addToCart">+</button>
            <button @mouseover="showDelete()" class="added" v-else-if="showedDelete == false && cart.includes(item.id)" @click="addToCart">✔</button>
            <button v-else-if="showedDelete == true && cart.includes(item.id)" @mouseleave="hideDelete()"  @click="deleteFromCart">✗</button>

        </div>
    </div>
</template>

<script>
export default {
    name: 'FoodItem',
    data(){
        return {
            showedDelete: false
        }
    },
    methods: {
        addToCart() {
            this.$emit('addedToCart', this.item.id)
        },
        deleteFromCart() {
            
            this.$emit('deletedFromCart', this.item.id)
        },
        showDelete() {
            this.showedDelete = true
        },
        hideDelete() {
            this.showedDelete = false
        }
    },
    props: {
        item: Object,
        cart: Array
    }
}
</script>

<style scoped>
    .food_item {
        width: 30%;
        display: flex;
        flex-direction: column;
        align-items: center;    
        padding: 20px 20px;
        margin-right: 20px;
        margin-bottom: 20px;
        border-radius: 20px;
        border: 1px solid #ddd;
    }

    .food_item h3 {
        width: 100%;
    }

    .food_item .footer {
        margin-top: 20px;
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    .food_item .footer span {
        font-size: 32px;
        font-weight: bold;
    }

    .food_item .footer button {
        cursor: pointer;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        color: #fff;
        font-size: 24px;
        background: #335;
        border: 2px #335 solid ;
    }

    

    .food_item .footer button:hover {
        background: #556;
        border: 2px #556 solid ;
    }

    .food_item img {
        object-fit: scale-down;
        height: 180px;
        width: auto;
    }

    .food_item .footer .added {
        color: #335;
        background: #fff;
        border: 2px #335 solid ;
    }
    .food_item .footer .added:hover {
        color: #335;
        background: #fff;
        border: 2px #335 solid ;
    }

</style>