<template>
    <div class="food_item">
        <img :src="item.image">
        <h3>{{item.title}}</h3>
        <p>{{item.desc}}</p>
        <div class="footer">
            <span>${{item.price}}</span>
            <button>+</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FoodItem',
    props: {
        item: Object
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

</style>