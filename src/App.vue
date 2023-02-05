<template>
  
  <div id="app1">
    <h1>Conversor de Moedas $$$</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="EUR"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="USD"/>
      <Conversor moeda-a="USD" moeda-b="EUR"/>
    </div>
  </div>
</template>

<script>
import Conversor from "../src/components/Conversor.vue";
export default {
  name: "app",
  components: {
    Conversor
  }
};
</script>

<style>
#app{
  position: absolute;
  top: 0;
  background: linear-gradient(#4ff, #eee);
  width: 100vw;
  height: 100vw;
}
h1 {
  margin-top: 100px;
}
#app1 {
  margin: auto;
  max-width:900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.linha {
  
  display: flex;
  justify-content: space-around;
}
</style>
