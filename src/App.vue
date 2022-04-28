<template>
  <div class="app">
    <div class="container">
      <h1 class="title">Products</h1>
      <Title text="Add a new product" />
      <addProductForm :products="products" class="add-product" />

      <Title text="Add a new product" />
      <productList :products="products" />
    </div>
  </div>
</template>

<script>
import Title from "@/components/Titel.vue";
import productList from "@/components/product-list.vue";
import addProductForm from "@/components/add-product-form.vue";
export default {
  name: "App",
  components: {
    Title,
    productList,
    addProductForm,
  },
  data() {
    return {
      products: [
        { id: "001", name: "iPad", price: 800 },
        { id: "002", name: "iPad", price: 800 },
        { id: "003", name: "iPad", price: 800 },
        { id: "004", name: "iPad", price: 800 },
        { id: "005", name: "iPad", price: 800 },
      ],
    };
  },
};
</script>

<style lang="less">
.app{
   padding-top: 30px;
   padding-bottom: 60px;
}
.title {
  font-family: "Gilroy";
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  line-height: 44px;
  text-align: center;
  color: #000000;
}
.title {
  margin-bottom: 20px;
}
.add-product {
  margin-bottom: 30px;
}

@media (min-width: 991px) {
  .title {
    margin-bottom: 40px;
  }
  .add-product {
    margin-bottom: 100px;
  }
}
</style>
