<template>
  <div id="app">
    <h1>Drawing Interface</h1>

    <div id="drawing-interface">
      <DrawingInterface />
    </div>
  </div>
</template>

<script>
import DrawingInterface from "./components/DrawingInterface.vue";

export default {
  name: "App",
  components: {
    DrawingInterface,
  },
};
</script>

<style>
#app {
  width: 1366px;
  height: 1024px;
  margin: auto;
  font-family: sans-serif;
}

#app h1 {
  text-align: center;
}

#drawing-interface {
  width: 1024px;
  height: 768px;
  margin: auto;
  border: 1px dashed #aaa;
}
</style>
