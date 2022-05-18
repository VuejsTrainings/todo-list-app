<template>
  <div id="app" class="container">
    <div class="row">
      <img
        id="logo"
        class="col-12 col-sm-3 col-md-2 col-lg-1"
        alt="Vue logo"
        src="./assets/logo.png"
      />
      <h1 class="col-12 col-sm-9 col-md-10 col-lg-11">
        Todos App - version pro
      </h1>
    </div>
    <div class="row">
      <to-dos></to-dos>
    </div>
  </div>
</template>

<script>
import ToDos from "./components/TodosModule.vue";

export default {
  name: "App",
  components: {
    ToDos,
  },
};
</script>

<style>
#logo {
  width: 80px;
  height: 50px;
  margin: auto;
}
.break {
  flex-basis: 100%;
  height: 0;
}
</style>
