<template>
    <div class="cart">
        <button>
            <img src="https://api.iconify.design/akar-icons/cart.svg?color=white">
            <div v-if="cart.length > 0" class="badge">{{cart.length}}</div>
        </button>
        
    </div>
</template>
<script>
export default {
    props: {
        cart: Array
    }
}
</script>
<style scoped>
    .cart {
        width: 100%;
        margin-bottom: 20px;
        display: flex;
        justify-content: flex-end;
    }
    .cart button {
        position: relative;
        width: 60px;
        height: 60px;
        padding: 16px;
        cursor: pointer;
        border-radius: 20px;
        background: #323142;
        border: none;
    }
    .cart button:hover {
        background: #323189;
    }
    .cart img {
        width: auto;
        height: 100%;
    }

    .badge {
        position: absolute;
        top: -4px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: #fff;
        right: -4px;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background: #d56;
    }
</style>