<template>
    <div class="cart">
        <button><img src="https://api.iconify.design/akar-icons/cart.svg?color=white"></button>
    </div>
</template>
<script>
export default {
    
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
</style>