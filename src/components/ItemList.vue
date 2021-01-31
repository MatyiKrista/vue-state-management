<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">
        Available items
      </p>
    </header>
    <section class="card-content">
      <ul>
        <li v-for="item in items" class="mb-2" :key="item.id">
          <item-list-element
              @add="$emit('add', $event)"
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
    </footer>
  </div>
</template>

<script>
import ItemListElement from "@/components/ItemListElement";

export default {
  name: "ItemList",
  components: {ItemListElement},
  props: {
    items: Array
  }
}
</script>

<style scoped>

</style>
