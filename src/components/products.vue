<template>
  <div v-for="(product, index) in products" :key="index">
    <div class="product" v-if="product.id">
      <h4 class="product-info product__id">{{ product.id }}</h4>
      <h4 class="product-info product__name">{{ product.name }}</h4>
      <h4 class="product-info product__price">{{ product.price }}</h4>
      <h4 v-if="product.id" class="product-info product__action">
        <button @click="deleteFunc(index)" class="product__btn">
          <img src="@/assets/icons/Delete.svg" alt="icon" />
        </button>
        <button class="product__btn">
          <img src="@/assets/icons/Edit.svg" alt="icon" />
        </button>
        <button class="product__btn">
          <img src="@/assets/icons/Show.svg" alt="icon" />
        </button>
      </h4>
    </div>
  </div>
</template>

<script>
export default {
  props: ["products"],
  methods: {
    deleteFunc(index) {
      this.products[index] = "";
      this.products.filter((element) => {
        return element[index] !== "";
      });
    },
  },
};
</script>

<style>
.product {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid rgba(2, 17, 33, 0.1);
  padding: 10px 0;
}
.product-info {
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  color: #021121;
  text-align: left;
  flex: 0 1 28%;
}
.product-info:last-child {
  flex: 0 1 16%;
}
.product__btn {
  background: transparent;
  margin-right: 14px;
}
</style>