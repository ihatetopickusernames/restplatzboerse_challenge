<template>
  <h1>Restplatzboerse Challenge</h1>
  <h2>Subtitel</h2>
  <h3>Tier</h3>
  <div class="price"><span class="price-label">ab</span> € 245</div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "./components/HelloWorld.vue";
require("@/assets/main.scss");

@Options({
  components: {
    HelloWorld,
  },
})
export default class App extends Vue {}
</script>
