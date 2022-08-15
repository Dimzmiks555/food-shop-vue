<template>
  <Layout>
    <div class="wrapper">
      <div class="left">
        <div class="header">
          <h1>Добро пожаловать! 😎</h1>
          <div></div>
        </div>
        <CategoryList></CategoryList>
        <FoodList></FoodList>
      </div>
      <div class="right">
          <Cart></Cart>
          <Offer></Offer>
          <ArticleList></ArticleList>
      </div>
    </div>
  </Layout>
</template>

<script>
// @ is an alias to /src
import Layout from '@/layouts/Layout.vue';
import CategoryList from '@/components/CategoryList.vue';
import FoodList from '@/components/FoodList.vue';
import Offer from '@/components/Offer.vue';
import ArticleList from '@/components/ArticleList.vue';
import Cart from '@/components/Cart.vue';

export default {
  name: 'HomeView',
  components: {
    Layout,
    CategoryList,
    FoodList,
    Offer,
    ArticleList,
    Cart
}
}
</script>

<style scoped>
  .header {
    display: flex;
    justify-content: space-between;
  }

  .wrapper {
    display: flex;
  }

  .left {
    width: 68%;
    margin-right: 20px;
  }
  .right {
    width: 30%;
  }

</style>