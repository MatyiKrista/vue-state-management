<template>
  <main id="app">
    <div class="container pt-6">
      <h1 class="title">Vue Market</h1>
      <div class="columns">
        <div class="column">
          <item-list
              :items="items"
              @add="addToCart"
          />
        </div>
        <div class="column">
          <cart-list
              :items="cartItems"
              @clear="clearCart"
              @remove="removeFromCart"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import items from "@/assets/items.json";
import ItemList from "@/components/ItemList";
import CartList from "@/components/CartList";

export default {
  name: 'App',
  components: {
    CartList,
    ItemList

  },
  data() {
    return {
      items: {
        "All items": [...items]
      },
      cartItems: []
    }
  },
  methods: {
    addToCart(item) {
      this.cartItems.push(item)
    },
    removeFromCart(item) {
      this.cartItems.splice(this.cartItems.indexOf(item), 1);
    },
    clearCart() {
      this.cartItems = [];
    }
  }
}
</script>
