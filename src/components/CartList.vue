<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">
        Cart
      </p>
    </header>
    <section class="card-content">
      <ul>
        <li v-for="item in items" class="mb-2" :key="item.id">
          <cart-list-element
              @clear="$emit('clear')"
              @remove="$emit('remove', $event)"
              :item="item"
          />
        </li>
      </ul>
    </section>
    <footer class="card-footer">
      <div class="card-footer-item">
        <p class="is-size-7">
          {{ items.length }} items
        </p>
      </div>
      <div class="card-footer-item">
        <a class="is-size-7" @click="$emit('clear')">
          Clear items
        </a>
      </div>
    </footer>
  </div>
</template>

<script>
import CartListElement from "@/components/CartListElement";
export default {
  name: "CartList",
  components: {
    CartListElement
  },
  props: {
    items: Array
  }
}
</script>

<style scoped>

</style>
