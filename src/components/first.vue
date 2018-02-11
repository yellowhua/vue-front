<template>
  <div id="first">

  </div>
</template>

<script>
export default {
  mounted() {
    document.getElementById('first').style.height = window.innerHeight + "px";
    this.initEcharts();
  },

  methods: {
    initEcharts() {
      var myEcharts = this.echarts.init(document.getElementById('first'));
      var option = {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [{
          data: [820, 932, 901, 934, 1290, 1330, 1320],
          type: 'line'
        }]
      };
      myEcharts.setOption(option);

      //浏览器窗口大小改变时，重新调整echarts的大小
      window.onresize = function temp() {
        myEcharts.resize();
      }
    }
  }
}
</script>
