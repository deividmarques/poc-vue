<template>
  <div class="speakers">
    <ul>
      <li v-for="speaker in speakers">
        <h3>{{ speaker.time }}</h3>
        <h2>{{ speaker.name }}</h2>
        <p>{{ speaker.bio }}</p>
        <a :href="speaker.social" class="photo" target="_blank"><img :src="speaker.image" alt=""></a>
        <h3>{{ speaker.talk }}</h3>
        <p>{{ speaker.description }}</p>
        <hr>
      </li>
    </ul>
  </div>

</template>

<script>

  import Vue from 'vue';

  Vue.use(require('vue-resource'));

export default {
  data () {
    return {
      speakers: []
    }
  },
  mounted () {
    var self = this;
    self.$http.get('src/data/data.json').then(function(response) {
        self.speakers = response.data;
      });
    }
  }
</script>

<style>
  .photo img {
    width: 120px;
    height: 120px;
  }
</style>
