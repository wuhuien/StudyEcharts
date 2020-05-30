<template>
  <div>
    <div id="xline"></div>
  </div>
</template>
<script>
export default {
  mounted() {
    var chart = this.$echarts.init(document.getElementById("xline"));
    var Colors = ["#10B9E7","#F57474","#56D0E3","#F8B448","#F8B78F"]
    var option = {
      title: {
        text: "技术学习次数",
        subtext: "纯属虚构"
      },
      tooltip: {
        trigger: "axis",
        axisPointer: {
          type: "shadow"
        }
      },
      legend: {
        data: [ "条","框"],
        show:false
      },
      grid: {
        left: "3%",
        right: "4%",
        bottom: "3%",
        containLabel: true
      },
      xAxis: {
        show:false
      },
      yAxis: [
          {
        type: "category",
        data: ["HTML5", "CSS3", "javaScript", "VUE", "NODE"],
        axisLine:{
            show:false
        },
        axisTick:{
            show:false
        },
      },
      {
          type:"category",
          show:true,
          data:[702,350,610,793,664],
          axisLine:{
              show:false
          },
          axisTick:{
              show:false
          },
          axisLabel:{
              textStyle:{
                fontSize:12,
                color:"gray"
              }
          },
      }
      ],
      series: [
        {
          name: "条",
          type: "bar",
          data: [70, 34, 60, 78, 69],
          itemStyle:{
              normal:{
                  barBorderRadius:20,
                  color:function(params){
                    //   var num = Colors.length;
                    // console.log(Colors[params.dataIndex])
                      return Colors[params.dataIndex];
                  }
              }
          },
          barCategoryGap:50,
          barWidth:10,
          label:{
              normal:{
                  show:true,
                  position:"inside",
                  formatter:"{c}%"
              }
          },
        yAxisIndex:0,
        //   
        },
        {
          name: "框",
          type: "bar",
        //   yAxisIndex:1,
          barCategoryGap:50,
          barWidth:15,
          itemStyle:{
              color:"none",
              borderColor:"#00C1DE",
              borderWidth:3,
              barBorderRadius:15
          },
          data: [100,100,100,100,100],
        yAxisIndex:1,
        }
      ]
    };
    chart.setOption(option)
  }
};
</script>
<style scoped>
#xline{
    width:500px;
    height:500px;
}
</style>