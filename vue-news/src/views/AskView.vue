<template>
  <div>
    <!-- <div v-for="item in askItems">{{ item.title }}</div> -->
    <p v-for="item in fetchedAsk">
      <a :href="item.url">{{ item.title }}</a>
      <small>{{ item.time_ago }}, {{ item.user }}</small>
    </p>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
  computed: {
    ...mapGetters({
      fetchedAsk : 'fetchedAsk'
    }),
  },
  created() {
    this.$store.dispatch('FETCH_ASK');
   
  }
}
</script>

<style>

</style>