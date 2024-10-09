<template>
  <div>
    <slot name:default>
    </slot> 
  </div>
</template>

<style scoped>
  div {
    background: white;
    border-radius: .25rem;
    border: 1px solid #ddd;
    padding: 1rem .75rem;
    margin-top: 1.5rem;
    box-shadow: 2px 3px 3px #eee;
  }
</style>