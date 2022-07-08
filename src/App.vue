<template>
  <main class="container mt-1 mb-1">
    <TeaserSlider> </TeaserSlider>
  </main>
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
