<template>
  <div>
    <input v-model="query" type="search" pattern=".*\S.*" required />
    <button @keypress.prevent="fetchWeather" class="search-btn">
      <span>Search</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  data() {
    return {
      api_key: "f6a2c317f97367bfe8fa3e5fc517e80d",
      url_base: "https://api.openweathermap.org/data/2.5/",
      query: "",
      weather: {},
    };
  },
  methods: {
    fetchWeather(e) {
      if (e.key == "Enter") {
        fetch(
          `${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`
        )
          .then((response) => {
			console.log(response)
            return response.json();
          })
          .then(this.setResults);
      }
    },
    setResults(results) {
      this.weather = results;
    },
  },
};
</script>

<style scoped>

</style>
