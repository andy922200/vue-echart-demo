<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div class="wrapper">
      <div class="pie-chart">
        <v-chart :option="pieOption" style="height:600px;width:600px;"/>
      </div>
      <div class="pie-chart">
        <v-chart style="height:600px;width:600px;"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'About',
  data () {
    return {
      pieOption: {
        title: {
          text: 'Traffic Sources',
          left: 'center'
        },
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b} : {c} ({d}%)'
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          data: [
            'Direct',
            'Email',
            'Ad Networks',
            'Video Ads',
            'Search Engines'
          ]
        },
        series: [
          {
            name: 'Traffic Sources',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
              { value: 335, name: 'Direct' },
              { value: 310, name: 'Email' },
              { value: 234, name: 'Ad Networks' },
              { value: 135, name: 'Video Ads' },
              { value: 1548, name: 'Search Engines' }
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            }
          }
        ]
      }

    }
  }
})
</script>

<style lang="scss">
.wrapper{
  display: flex;
  justify-content: center;

  .pie-chart{
    width:50%;
  }
}
</style>
