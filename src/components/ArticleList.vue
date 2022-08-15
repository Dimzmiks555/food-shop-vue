<template >
    <div class="articles">
        <h2>Статьи</h2>
        <div class="article_list">
            <ArticleItem v-for="item in articles" :item="item"></ArticleItem>
        </div>
    </div>
</template>
<script>
import ArticleItem from './ArticleItem.vue';
export default {
    name: "ArticleList",
    components: { ArticleItem },
    data(){
        return {
            articles: [
                {
                    id: 1,
                    image: '😷',
                    title: 'Ограничения во время коронавируса',
                    rate: 86
                },
                {
                    id: 2,
                    image: '🌯',
                    title: 'История мексиканской кухни',
                    rate: 54
                },
                {
                    id: 3,
                    image: '🍚',
                    title: 'Как выбрать суши правильно?',
                    rate: 102
                },
            ]
        }
    }
}
</script>
<style scoped>
    .articles {
        margin-top: 30px;
    }
    .article_list {

    }
</style>