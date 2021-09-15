<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld
      :client="this.VueShowClient.currentClient"
      @returnClient="addUserApp"
    />
    <h1>{{ mojedane.imie }}</h1>
    <h1>{{ mojedane.nazwisko }}</h1>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld,
  },
  data: () => ({
    VueShowClient: {},
    mojedane: { imie: "", nazwisko: "" },
  }),
  mounted() {
    this.VueShowClient = this.coachViewContext.binding.value;
  },
  methods: {
    addUserApp(Object) {
      this.mojedane = Object;
    },
  },
};
</script>
