<template>
  <div class="weatherdetails__main">
    <div class="weatherdetails__container">
      <span class="weatherdetails__main-title">{{ options.params.q }}</span>
      <span class="weatherdetails__subtitle">Sunday 12 January 2020</span>
      <div class="weatherdetails__degrees">
        <span class="weatherdetails__degrees-title">27^c</span>
      </div>
      <span class="weatherdetails__weather-condition">Clouds</span>
    </div>
    <button @click.prevent="makeRequest">Fazer Request</button>
  </div>
</template>

<script>
const axios = require("axios");

export default {
  name: "WeatherDetails",
  data() {
    return {
      options: {
        method: "GET",
        url: "https://community-open-weather-map.p.rapidapi.com/weather",
        params: {
          q: "London, UK",
          lat: "0",
          lon: "0",
          callback: "test",
          id: "2172797",
          lang: "null",
          units: "imperial",
          mode: "xml",
        },
        headers: {
          "X-RapidAPI-Host": "community-open-weather-map.p.rapidapi.com",
          "X-RapidAPI-Key":
            "25a50a7329mshd6dba41267b3948p1c0c3djsnd3513099cf73",
        },
      },
    };
  },
  methods: {
    makeRequest() {
      axios
        .request(this.options)
        .then(function (response) {
          console.log(response);
          console.log(response.data);
        })
        .catch(function (error) {
          console.error(error);
        });
    },
  },
};
</script>

<style scoped>
* {
  color: #fff;
}

.weatherdetails__main {
  display: flex;
}

.weatherdetails__container {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  text-align: center;
}

.weatherdetails__main-title {
  font-size: 24px;
  font-weight: bold;
}

.weatherdetails__subtitle {
  font-size: 18px;
  font-style: italic;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
  margin: 10px;
}

.weatherdetails__degrees {
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  padding: 40px 60px;
  margin: 20px;
  border-radius: 20px;
}

.weatherdetails__degrees-title {
  font-size: 48px;
  font-weight: bold;
}

.weatherdetails__weather-condition {
  font-size: 32px;
  font-weight: bold;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
