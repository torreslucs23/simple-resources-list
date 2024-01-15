<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Stored reources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButtonMode"
      >Add resources</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import AddResource from './AddResource.vue';
import StoredResources from './StoredResources.vue';

export default {
  components: {
    StoredResources,
    AddResource,
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  data() {
    return {
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official guide',
          description: 'The official vueJs documentation',
          link: 'https://vuejs.org/',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn how to google...',
          link: 'https://google.com',
        },
      ],
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab() {
      if (this.selectedTab === 'stored-resources') {
        this.selectedTab = 'add-resource';
      } else {
        this.selectedTab = 'stored-resources';
      }
    },
  },
};
</script>
