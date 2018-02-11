<template>
  <div id="forth">

  </div>
</template>

<script>
export default {
  mounted() {
    document.getElementById('forth').style.height = window.innerHeight + "px";
    this.initEcharts();
  },

  methods: {
    initEcharts() {
      var myEcharts = this.echarts.init(document.getElementById('forth'));
      var option = {
        angleAxis: {
        },
        radiusAxis: {
          type: 'category',
          data: ['周一', '周二', '周三', '周四'],
          z: 10
        },
        polar: {
        },
        series: [{
          type: 'bar',
          data: [1, 2, 3, 4],
          coordinateSystem: 'polar',
          name: 'A',
          stack: 'a'
        }, {
          type: 'bar',
          data: [2, 4, 6, 8],
          coordinateSystem: 'polar',
          name: 'B',
          stack: 'a'
        }, {
          type: 'bar',
          data: [1, 2, 3, 4],
          coordinateSystem: 'polar',
          name: 'C',
          stack: 'a'
        }],
        legend: {
          show: true,
          data: ['A', 'B', 'C']
        }
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
