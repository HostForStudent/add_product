<template>
  <div class="table">
    <div class="table__header">
      <h4 class="table__title">Product ID</h4>
      <h4 class="table__title">Product Name</h4>
      <h4 class="table__title">Product Price</h4>
      <h4 class="table__title">Action</h4>
    </div>
    <div class="table__products">
      <products :products="products" />
    </div>
  </div>
</template>

<script>
import products from "@/components/products.vue";
export default {
  props: ["products"],
  components: {
    products,
  },
};
</script>

<style>
.table {
  padding: 20px 27px;
  border: 1px solid rgba(22, 114, 213, 0.25);
}
.table__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 2px solid rgba(2, 17, 33, 0.5);
  padding: 10px 0;
}
.table__title {
  text-align: left;
  flex: 0 1 28%;
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  color: #021121;
}
.table__title:last-child {
  flex: 0 1 16%;
}
.table__products {
}
</style>