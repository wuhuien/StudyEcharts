<template>
  <div id="app">
    <NewEcharts />
    <EchartsOne />
    <Echart />
    <Cmap />
    <DoubleLine />
    <Measurement />
    <Map />
    <Stack />
    <Examples />
    <Alloc />
    <Demo />
    <Xline />
  </div>
</template>

<script>
import NewEcharts from "./components/NewEcharts";
import EchartsOne from "./components/EchartsOne";
import Echart from "./components/Echarts_01";
import Cmap from "./components/ChineMap";
import DoubleLine from "./components/DoubleLine";
import Measurement from "./components/Measurement";
import Map from "./components/Map";
import Stack from "./components/Stack";
import Examples from "./components/Examples";
import Alloc from "./components/Alloc";
import Demo from "./components/demo";
import Xline from "./components/Xline";

export default {
  name: 'App',
  components: {
    NewEcharts,
    EchartsOne,
    Echart,
    Cmap,
    DoubleLine,
    Measurement,
    Map,
    Stack,
    Examples,
    Alloc,
    Demo,
    Xline
  },
  mounted(){
   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
