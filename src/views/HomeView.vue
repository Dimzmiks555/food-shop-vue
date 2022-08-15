<template>
  <Layout>
    <div class="wrapper">
      <div class="left">
        <div class="header">
          <h1>Добро пожаловать! 😎</h1>
          <Search @searched="searchFood" :search="search"></Search>
        </div>
        <CategoryList :categories="categories" :selected="selected" @selected="select"></CategoryList>
        <FoodList :cart="cart"  @deletedFromCart="deleteFromCart" @addedToCart="addToCart" :filteredFood="filteredFood" :selected="selected"></FoodList>
      </div>
      <div class="right">
          <Cart :cartOpened="cartOpened" @showed="showCard" :cart="cart"></Cart>
          <div v-if="!cartOpened">
            <Offer></Offer>
            <ArticleList></ArticleList>
          </div>
          <CartBlock :cart="cart" :food="food" v-else></CartBlock>
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
import Search from '@/components/Search.vue';
import _food from '@/mockups/_food';
import _categories from '@/mockups/_categories';
import CartBlock from '@/components/CartBlock.vue';

export default {
  data() {
    return {
      selected: 0,
      cartOpened: false,
      cart: [],
      search: '',
      categories: _categories,
      filteredFood: [],
      food: _food
    }
    
  },
  methods: {
    select(id) {
        this.selected = id
    },
    searchFood(value) {
      
        this.selected = 0
        this.filteredFood = this.food.filter(item => item.title.toLocaleLowerCase().search(value.toLocaleLowerCase()) !== -1)
    },
    addToCart(id){
        this.cart.push(id)
    },
    deleteFromCart(id) {
        console.log(this.cart.filter(item => item != id))
        this.cart = this.cart.filter(item => item != id)
    },
    showCard() {
      this.cartOpened = !this.cartOpened
    }
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
  name: 'HomeView',
  components: {
    Layout,
    CategoryList,
    FoodList,
    Offer,
    ArticleList,
    Cart,
    Search,
    CartBlock
}
}
</script>

<style scoped>
  .header {
    display: flex;
    align-items: center;
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