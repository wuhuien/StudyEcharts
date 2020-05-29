<template>
  <div>
    <h1>全国降雨</h1>
    <div id="Cmap"></div>
  </div>
</template>
<script>
import "../assets/china"
export default {
  mounted() {
    //   地图需要的地址数据、随机数（应该是拿到后台给的数据）
    var  mydata = [  
                {name: '北京',value: '100' },{name: '天津',value: randomData() },  
                {name: '上海',value: randomData() },{name: '重庆',value: randomData() },  
                {name: '河北',value: randomData() },{name: '河南',value: randomData() },  
                {name: '云南',value: randomData() },{name: '辽宁',value: randomData() },  
                {name: '黑龙江',value: randomData() },{name: '湖南',value: randomData() },  
                {name: '安徽',value: randomData() },{name: '山东',value: randomData() },  
                {name: '新疆',value: randomData() },{name: '江苏',value: randomData() },  
                {name: '浙江',value: randomData() },{name: '江西',value: randomData() },  
                {name: '湖北',value: randomData() },{name: '广西',value: randomData() },  
                {name: '甘肃',value: randomData() },{name: '山西',value: randomData() },  
                {name: '内蒙古',value: randomData() },{name: '陕西',value: randomData() },  
                {name: '吉林',value: randomData() },{name: '福建',value: randomData() },  
                {name: '贵州',value: randomData() },{name: '广东',value: randomData() },  
                {name: '青海',value: randomData() },{name: '西藏',value: randomData() },  
                {name: '四川',value: randomData() },{name: '宁夏',value: randomData() },  
                {name: '海南',value: randomData() },{name: '台湾',value: randomData() },  
                {name: '香港',value: randomData() },{name: '澳门',value: randomData() }  
            ]; 

    function randomData() {  
     return Math.round(Math.random()*500);  
    } 
    var chart = this.$echarts.init(document.getElementById("Cmap"));
    var option = {
        // 整个图片表的背景色
      backgroundColor: "#FFFFFF",
      //是图标头部的标题
      title: {
          //标题内容
        text: "全国降雨分布图",
        //副标题
        subtext: "数据纯属虚构",
        //判断x轴文本处在哪个位置
        x: "center"
      },
      //移入某一个省份是的提示框
      tooltip: {
          //详细内容
        trigger: "item",
        //背景颜色
        // backgroundColor:"red"
      },

      //左侧小导航图标
      visualMap: {
          //默认是否显示false为不显示
        show: true,
        //定位的位置
        //这是横向的坐标位置
        x: "left",
        //这是纵向的坐标位置
        y: "top",
        //显示的数据列表
        splitList: [
          { start: 500, end: 600 },
          { start: 400, end: 500 },
          { start: 300, end: 400 },
          { start: 200, end: 300 },
          { start: 100, end: 200 },
          { start: 0, end: 100 }
        ],
        //显示的列表开始的盒子颜色
        color: [
          "#5475f5",
          "#9feaa5",
          "#85daef",
          "#74e2ca",
          "#e6ac53",
          "#9fb5ea"
        ]
      },

      //配置属性
      series: [
        {
            //提示框的标题
          name: "降雨量",
          //显示类型为地图
          type: "map",
          //中国的地图
          mapType: "china",
          //
          roam: true,
          //显示省份信息
          label: {
            normal: {
              show: true //省份名称
            },
            emphasis: {
              show: false
            }
          },
          data: mydata //数据
        }
      ]
    };
    //使用option定义的数据
    chart.setOption(option);
  }
};
</script>
<style scoped>
#Cmap {
  width: 900px;
  height: 900px;
}
</style>