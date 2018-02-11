<template>
  <div id="fivth">

  </div>
</template>

<script>
export default {
  mounted() {
    document.getElementById('fivth').style.height = window.innerHeight + "px";
    this.initEcharts();
  },

  methods: {
    initEcharts() {
      var myEcharts = this.echarts.init(document.getElementById('fivth'));
      var option = {
        tooltip: {
          trigger: 'item',
          formatter: "{a} <br/>{b}: {c} ({d}%)"
        },
        legend: {
          orient: 'vertical',
          x: 'left',
          data:['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
        },
        series: [
          {
            name:'访问来源',
            type:'pie',
            radius: ['50%', '70%'],
            avoidLabelOverlap: false,
            label: {
              normal: {
                show: false,
                position: 'center'
              },
              emphasis: {
                show: true,
                textStyle: {
                  fontSize: '30',
                  fontWeight: 'bold'
                }
              }
            },
            labelLine: {
              normal: {
                show: false
              }
            },
            data:[
              {value:335, name:'直接访问'},
              {value:310, name:'邮件营销'},
              {value:234, name:'联盟广告'},
              {value:135, name:'视频广告'},
              {value:1548, name:'搜索引擎'}
            ]
          }
        ]
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
