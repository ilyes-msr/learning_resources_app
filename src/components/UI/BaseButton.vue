<template>
  <button :class="className" :type="type">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    className: {
      type: String,
      required: false
    },
    type: {
      type: String,
      required: false,
      default: 'button'
    }
  }
}
</script>

<style scoped>
  button {
    border: none;
    padding: .5rem 1rem;
    border-radius: .25rem;
    cursor: pointer;
    margin-left: .25rem;
    margin-right: .25rem;
  }
  button:hover {
    opacity: .75;
  }
  .primary {
    background-color: coral;
    color: white;
  }
  .dark-primary {
    background-color: rgb(204, 101, 64);
    font-weight: bold;
  }
  .secondary {
    background-color: #2F5061;
    color: white;
  }
  .dark-secondary {
    background-color: #1e323c;
    font-weight: bold;
  }
  .btn-big {
    padding: .75rem 1.25rem;
    font-size: 1.25rem;
  }
</style>