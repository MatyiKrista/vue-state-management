<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">
        Available items
      </p>
    </header>
    <section class="card-content">
      <b-collapse v-for="(itemGroup, key) in items">
        <template v-slot:trigger="{ open }">
          <a
              class="is-flex is-justify-content-space-between is-align-items-center mb-3 has-text-black"
              style="border-bottom: 1px solid black;"
          >
            <p>{{ key }}</p>
            <strong v-html="open ? '&#8593;' : '&#8595;'"></strong>
          </a>
        </template>
        <ul>
          <li v-for="item in itemGroup" class="mb-2" :key="item.id">
            <item-list-element
                @add="$emit('add', $event)"
                :item="item"
            />
          </li>
        </ul>
      </b-collapse>
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
