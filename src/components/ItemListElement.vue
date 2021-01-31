<template>
  <article class="media">
    <figure class="media-left">
      <p v-html="item.emoji"></p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p>
          {{item.name}}
        </p>
      </div>
    </div>
    <div class="media-right">
      <b-button
          type="is-success"
          @click="$emit('add', item)"
      >
        Add to cart
      </b-button>
    </div>
  </article>
</template>

<script>
export default {
  name: "ItemListElement",
  props: {
    item: Object
  }
}
</script>

<style scoped>

</style>
