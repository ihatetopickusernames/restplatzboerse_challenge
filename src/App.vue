<template>
  <!--  <h1>Restplatzboerse Challenge</h1>-->
  <!--  <h2>Subtitel</h2>-->
  <!--  <h3>Tier</h3>-->
  <!--  <div class="price"><span class="price-label">ab</span> € 245</div>-->
  <TeaserSlider> </TeaserSlider>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TeaserSlider from "./components/TeaserSlider.vue";
require("@/assets/main.scss");

@Options({
  components: {
    TeaserSlider,
  },
})
export default class App extends Vue {}
</script>
