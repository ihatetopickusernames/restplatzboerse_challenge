<template>
  <div class="is-flex is-justify-content-space-between">
    <div>
      <h1>Zootiere</h1>
      <h2 class="ellipsis">Zufällige Auswahl an Zootieren</h2>
    </div>
    <a
      href="https://www.restplatzboerse.at/"
      title="Zur Restplatzbörse Startseite."
      >Alle</a
    >
  </div>
  <div class="slider-content grid-display">
    <div class="card" v-for="animal in animals" :key="animal.id">
      <div class="card-image">
        <figure class="image is-5by3">
          <img :src="animal.image_link" :alt="animal.name" />
        </figure>
      </div>
      <div class="card-content">
        <div class="media-content">
          <div class="is-flex is-justify-content-space-between">
            <!-- added accessibility with tabindex property. users can now access content by pressing tab key. -->
            <h3 class="ellipsis" tabindex="0">{{ animal.name }}</h3>
            <div class="weight has-text-right ellipsis">
              <span class="weight-label">bis zu</span>
              {{ animal.weight_max }} kg
            </div>
          </div>
        </div>
      </div>
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

<style lang="scss">
@import "./TeaserSlider.scss";
</style>
