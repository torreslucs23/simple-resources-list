<template>
  <the-header title="Remember me"></the-header>
  <stored-resource :resources="storedResources"></stored-resource>
</template>

<script>
import TheHeaderVue from './components/layouts/TheHeader.vue';
import StoredResources from './components/learning-resources/StoredResources.vue';
export default {
  components: {
    'stored-resource': StoredResources,
    'the-header': TheHeaderVue,
  },
  data() {
    return {
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
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
