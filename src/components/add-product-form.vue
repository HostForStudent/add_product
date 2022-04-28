<template>
  <div @submit.prevent class="c-form">
    <div class="c-form__row">
      <div class="c-form__label">
        <span>ID</span>
        <input @input="idfunc" class="c-form__input" type="number" />
      </div>
      <div class="c-form__label">
        <span>Name</span>
        <input @input="namefunc" class="c-form__input" type="text" />
      </div>
      <div class="c-form__label">
        <span>Price</span>
        <input @input="pricefunc" class="c-form__input" type="number" />
      </div>
      <button @click="addObject" class="c-form__btn">Add</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["products"],
  data() {
    return {
      id: "",
      name: "",
      price: "",
    };
  },
  methods: {
    idfunc(e) {
      if (e.target.value > 99) {
        this.id = e.target.value;
      } else if (e.target.value > 9) {
        this.id = "0" + e.target.value;
      } else {
        this.id = "00" + e.target.value;
      }
    },
    namefunc(e) {
      this.name = e.target.value;
    },
    pricefunc(e) {
      this.price = e.target.value;
    },
    addObject() {
      this.products.push({ id: this.id, name: this.name, price: this.price });
    },
  },
};
</script>

<style>
.c-form {
  padding: 16px 27px;
  border: 1px solid rgba(22, 114, 213, 0.25);
  box-sizing: border-box;
}
.c-form__row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}
.c-form__label {
  font-weight: 500;
  font-size: 18px;
  line-height: 21px;
  margin: 8px;
  color: #021121;
}
.c-form__input {
  width: 220px;
  height: 33px;
  border: 1px solid rgba(22, 114, 213, 0.25);
  margin-left: 9px;
  padding: 0 20px;
}
.c-form__btn {
  width: 75px;
  height: 33px;
  background: #1672d5;
  border-radius: 3px;
  font-weight: 500;
  font-size: 18px;
  line-height: 21px;
  margin: 8px;
  margin-left: auto;
  color: #ffffff;
}
@media (max-width: 620px) {
  .c-form__row {
    justify-content: start;
  }
  .c-form__label {
    font-size: 14px;
  }
  .c-form__label > span {
    display: block;
  }
  .c-form {
    padding: 5px 10px;
  }
}
</style>