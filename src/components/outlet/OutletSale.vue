<template>
  <div class="books" @click="goToCart()">
    <h2>{{ book.Title }}</h2>
    <h4>Type: {{ book.Type }}</h4>
    <h3>{{ book.Price }} :-</h3>
    <img :src="book.Img" alt="bild" />
    <div>
      <button @click="add(book)" class="addButton">Add to cart</button>
    </div>
  </div>
</template>

<script>
import data from "../../assets/products.json";
export default {
  name: "OutletSale",
  props: {
    book: Object,
  },
  computed: {
    cartItems() {
      return data.cart;
    },
  },
  methods: {
    goToCart() {
      //this.$router.push(`/BookInfo/${id}`);
    },
    add(cart) {
      this.cartItems.push({
        id: cart.id,
        Title: cart.Title,
        Price: cart.Price,
        Type: cart.Type,
        Img: cart.Img,
      });
    },
  },
};
</script>

<style scoped>
.books {
  margin: 15px;
  padding: 1rem;
  border: 1px solid rgba(15, 15, 15, 0.329);
  background-color: #c9c9c750;
  box-shadow: 0 0 7px rgba(43, 41, 41, 0.623);
  width: 240px;
  float: left;
  color: #3d2f27;
}
.books img {
  width: 200px;
  height: 160px;
}
.addButton {
  float: right;
  display: block;
  text-decoration: none;
  background: #705546;
  color: #eeeeee;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 15px;
  text-align: center;
  font-family: Arial, Helvetica, sans-serif;
  transition: 0.7s;
  letter-spacing: 1px;
  width: 180px;
  margin-right: 30px;
  align-self: start;
}
.addButton:hover {
  background: #3d2f27;
  color: #ffffff;
  transition: 0.7s;
  cursor: pointer;
}
.addButton span {
  float: left;
}
</style>