<template >
    <div @click="select()" class="category" :class="item.id == selected && 'active'">
        <img :src="item.image">
        <p>{{item.title}}</p>
    </div>
</template>
<script>
export default {
    props: {
        selected: Number,
        item: Object
    },
    methods: {
        select(){
            this.$emit('selected', this.item.id)
        }
    }
}
</script>
<style scoped>
    .category {
        cursor: pointer;
        background: #f5f6f7;
        width: 120px;
        padding: 30px 20px;
        border-radius: 30px;
        margin-right: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        border: 2px solid #fff;
    }
    .category:hover {
        background: #e5e6e7;
    }
    .category img {
        margin-bottom: 20px;
        width: auto;
        height: 80px;
    }

    .active {
        background: #fff;
        box-shadow: 0 4px 10px #ddd;
        /* border: 2px solid #ccc; */
    }
    .active:hover {
        background: #fff;
        /* border: 2px solid #ccc; */
    }

</style>