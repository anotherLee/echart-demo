<template>
  <div id="app">
    <div ref="demo" id="echarts-demo"></div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {}
  },
  mounted() {
    this.draw();
  },
  methods: {
    draw() {
      let container = document.getElementById("echarts-demo")
      let chart = this.$echarts.init(container);
      let options = {
        series: [{
          type: 'liquidFill',
          name: "这是name",
          // 波浪
          data: [{
            name: '60%',
            value: 0.6
          }, 0.5, 0.4, 0.3],
          // 波浪的颜色
          //color: ["red", "yellow", "blue", "orange"],
          // 文字样式
          label: {
            formatter: '{b}',
            fontSize: 60,
            color: 'red',
            insideColor: 'yellow'
          },
        }],
        // 浮窗
        tooltip: {
          show: true
        }
      }
      chart.setOption(options);
    }
  },
  components: {
  }
}
</script>

<style>
* {
  margin: 0; padding: 0;
}
html, body, #app {
  height: 100%; height: 100%;
}
#app {
  display: flex; justify-content: center; align-items: center;
}

#echarts-demo {
  width: 600px; height: 600px;
}
</style>
