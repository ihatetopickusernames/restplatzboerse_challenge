<template>
  <h1>Zootiere</h1>
  <h2>Zufällige Auswahl an Zootieren</h2>
  <a href="https://www.restplatzboerse.at/" title="Zur Hauptseite">Alle</a>
  <div v-for="animal in animals" :key="animal.id" class="images">
    <img :src="animal.image_link" alt="{{animal.name}}" />
    <h3>{{ animal.name }}</h3>
    <div class="weight">
      <span class="weight-label">bis zu</span> {{ animal.weight_max }} kg
    </div>
  </div>
</template>

<script>
export default {
  name: "TeaserSlider",
  data: function () {
    return {
      animals: [],
    };
  },

  mounted() {
    fetch("https://zoo-animal-api.herokuapp.com/animals/rand/5")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        console.log(data);
        this.animals = data;
      })
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>

<style scoped></style>
