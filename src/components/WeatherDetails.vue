<template>
  <div class="weatherdetails__main">
    <div class="weatherdetails__container">
      <span class="weatherdetails__main-title">Nigeria, NG</span>
      <span class="weatherdetails__subtitle">Sunday 12 January 2020</span>
      <div class="weatherdetails__degrees">
        <span class="weatherdetails__degrees-title">27^c</span>
      </div>
      <span class="weatherdetails__weather-condition">Clouds</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "WeatherDetails",
  data() {
    return {};
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
  background-color:rgba(255, 255, 255, 0.25);
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
