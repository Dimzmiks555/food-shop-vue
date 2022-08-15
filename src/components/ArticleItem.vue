<template>
    <div class="article_item">
        <div class="image_wrapper">
            <p>{{item.image}}</p>
        </div>
        <div class="info">
            <h3>{{item.title}}</h3>
            <span>👍 {{item.rate}}</span>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ArticleItem',
    props: {
        item: Object
    }
}
</script>
<style scoped>
    .article_item {
        display: flex;
        margin-bottom: 20px;
    }
    .image_wrapper {
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 42px;
        margin: 0;
        padding: 0;
        min-width: 100px;
        margin-right: 20px;
        height: 100px;
        background: #eef;
        border-radius: 30px;
    }
    .info {
        padding: 10px 0;
    }
    .article_item h3 {
        font-size: 18px;
        margin-top: 0
    }
    .article_item span {
        background: #fef6dd;
        padding: 6px 10px;
        border-radius: 10px;
    }
</style>