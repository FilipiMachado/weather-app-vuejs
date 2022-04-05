<template>
  <div class="main-content">
    <div class="main-content__header">
      <SearchBar />
    </div>
    <div class="main-content__section">
      <WeatherDetails />
    </div>
  </div>
</template>

<script>
import SearchBar from "../components/SearchBar.vue";
import WeatherDetails from "../components/WeatherDetails.vue";

export default {
  name: 'HomeView',
  components: {
    SearchBar,
    WeatherDetails,
  },
  data() {
    return {}
  },
  methods: {},
}
</script>

<style scoped>
.main-content {
  background-image: linear-gradient(to right, #9600FF , #AEBAF8);
}
</style>
