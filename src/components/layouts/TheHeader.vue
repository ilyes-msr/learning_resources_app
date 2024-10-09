<template>
  <h1>{{title}}</h1>
</template>

<script>
export default {
  props: ['title']
}
</script>

<style scoped>
  h1 {
    text-align: center;
    background: coral;
    margin-top: 0;
    padding: 1rem;
    color: white;
  }
</style>