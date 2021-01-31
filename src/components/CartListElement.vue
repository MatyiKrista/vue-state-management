<template>
  <article class="media">
    <figure class="media-left">
      <p v-html="item.emoji"></p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p>
          {{ item.name }}
        </p>
      </div>
    </div>
    <div class="media-right">
      <b-button
          type="is-danger"
          @click="$emit('remove', item)"
      >
        Remove from cart
      </b-button>
    </div>
  </article>
</template>

<script>
export default {
  name: "CartListElement",
  props: {
    item: Object
  }
}
</script>

<style scoped>

</style>
