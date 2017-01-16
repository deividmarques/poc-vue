<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <speakers></speakers>
  </div>
</template>

<script>

import Speakers from './Speakers.vue';

export default {
  name: 'app',
  components: {Speakers}
}
</script>