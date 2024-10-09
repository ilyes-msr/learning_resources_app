<template>
    <li>
      <base-card>
        <template #default>
          <header>
            <h3>{{ title }}</h3>
            <base-button class="secondary" @click="removeResource">Delete</base-button>
          </header>
          <p>{{ description }}</p>
          <nav>
            <a :href="link">{{ link }}</a>
          </nav>
        </template> 
      </base-card>
    </li>
</template>

<script>
export default {
  inject: ['deleteResource'],
  props: {
    id: {
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    },
  },
  methods: {
    removeResource() {
      this.deleteResource(this.id);
    }
  },
  data() {
   return {};        
},

}
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}
p {
  margin: 0.5rem 0;
}
a {
  text-decoration: none;
  color: #ce5c00;
}
a:hover,
a:active {
  color: #c89300;
}
</style>