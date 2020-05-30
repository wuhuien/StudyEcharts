<template>
  <div>
    <div id="main2"></div>
  </div>
</template>
<script>
export default {
  mounted() {
    var echarts = this.$echarts.init(document.getElementById("main2"))
    function num(){
        return parseInt(Math.random()*300)
    }
    var option = {
      title: {
        text: "统计销量图",
        subtext:"纯属虚构"
      },
      tooltip: {
        trigger: "axis",
        axisPointer: {
          type: "cross",
          label: {
            backgroundColor: "#6a7985"
          }
        }
      },
      legend: {
        data: ["烟酒销量", "书本销量"]
      },
      toolbox: {
        feature: {
          saveAsImage: {}
        }
      },
      grid: {
        left: "3%",
        right: "4%",
        bottom: "3%",
        containLabel: true
      },
      xAxis: [
        {
          type: "category",
          boundaryGap: false,
          data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"]
        }
      ],
      yAxis: [
        {
          type: "value"
        }
      ],
      series: [
        {
          name: "烟酒销量",
          type: "line",
          stack: "总量",
          areaStyle: {},
          data: [num(), num(), num(), num(), num(), num(), num()]
        },
        {
          name: "书本销量",
          type: "line",
          stack: "总量",
          areaStyle: {},
          data: [num(), num(), num(), num(), num(), num(), num()]
        }
      ]
    };
    echarts.setOption(option)
  }
};
</script>
<style scoped>
#main2{
    width:500px;
    height:500px;
}
</style>