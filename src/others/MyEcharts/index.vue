<template>
  <div class="my-echarts">
    <div ref="echartsPie" style="width: 100%;height: 500px;"></div>
  </div>
</template>

<script>
import * as Echarts from 'echarts'

export default {
  name: 'MyEcharts',
  data () {
    return {}
  },

  mounted() {
    this.init()
  },

  methods: {
    init () {
      this.setPie()
    },

    setPie () {
      let echartsPie = Echarts.init(this.$refs['echartsPie'])
      echartsPie.showLoading()

      setTimeout(() => {
        echartsPie.hideLoading()

        echartsPie.setOption({
          series: {
            type: 'pie',
            data: [
              {name: 'A', value: 1212},
              {name: 'B', value: 2323},
              {name: 'C', value: 1919}
            ]
          }
        })
      }, 1000)
    }
  }
}
</script>
