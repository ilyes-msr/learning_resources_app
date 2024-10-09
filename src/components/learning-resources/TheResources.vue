<template>
  <base-card>
    <div class="text-center">
      <base-button @click="toggleTab('stored-resources')" class="primary" :class="storedResourcesSelected">Stored Resources</base-button>
      <base-button @click="toggleTab('add-resource')" class="primary" :class="addResourceSelected">Add Resource</base-button>
    </div>
    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
  </base-card>
</template>
<script>

import AddResource from './AddResource.vue';
import StoredResources from './StoredResources.vue';

  export default {
    components: {
      AddResource,
      StoredResources
    },
    data() {
      return {
        selectedTab: 'stored-resources',
        storedLearningResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official documentation for the Vue framework',
          link: 'https://vuejs.org'
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Google search engine',
          link: 'https://google.com'
        },
      ]
      }
    },
    computed: {
      storedResourcesSelected() {
        return this.selectedTab === 'stored-resources' ? 'dark-primary' : null
      },
      addResourceSelected() {
        return this.selectedTab === 'add-resource' ? 'dark-primary' : null
      }
    },
    provide() {
      return {
        resources: this.storedLearningResources,
        addResource: this.addResource,
        deleteResource: this.deleteResource
      }
    },
    methods: {
      toggleTab(cmp) {
        this.selectedTab = cmp
      },
      addResource(title, description, link) {
        this.storedLearningResources.push({
          id: title, 
          title: title,
          description: description,
          link: link
        })
        this.toggleTab('stored-resources')
      },
      deleteResource(id) {
        const resIdx = this.storedLearningResources.findIndex(res => res.id === id)
        this.storedLearningResources.splice(resIdx, 1)
      }
    }
  }
</script>