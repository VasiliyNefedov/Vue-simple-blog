<template>
  <div class="post">
    <router-link :to="{name: 'Details', params: {id: post.id}}">
      <h3>{{ post.title }}</h3>
    </router-link>
    <p>{{ snippet }}</p>
    <span v-for="(tag, idx) in post.tags" :key="idx"> #{{ tag }}</span>
  </div>
</template>

<script>
import {computed} from 'vue'

export default {
  name: "SinglePost",
  props: ['post'],
  setup(props) {
    const snippet = computed(() => {
      return props.post.body.substring(0, 50) + '...'
    })
    return {snippet}
  }
}
</script>

<style scoped>

</style>