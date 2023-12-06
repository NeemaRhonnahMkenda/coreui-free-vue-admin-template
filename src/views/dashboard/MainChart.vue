<template>
  <CChart type="radar" :data="data" :options="options" ref="mainChartRef" />
</template>

<script>
import { onMounted, ref } from 'vue'
import { CChart } from '@coreui/vue-chartjs'
import { getStyle } from '@coreui/utils'

const random = (min, max) => Math.floor(Math.random() * (max - min + 1) + min)

export default {
  name: 'MainChartExample',
  components: {
    CChart,
  },
  setup() {
    const mainChartRef = ref()
    const data = {
      labels: ['Shots', 'Interceptions', 'Aerials', 'Minutes Played', 'Touches', 'Passes', 'Successful Tackles'],
      datasets: [
        {
          label: 'My Single Dataset',
          backgroundColor: `rgba(${getStyle('--cui-info-rgb')}, .1)`,
          borderColor: getStyle('--cui-info'),
          pointHoverBackgroundColor: getStyle('--cui-info'),
          borderWidth: 2,
          data: [
            random(50, 200),
            random(50, 200),
            random(50, 200),
            random(50, 200),
            random(50, 200),
            random(50, 200),
            random(50, 200),
          ],
          fill: true,
        },
      ],
    }

    const options = {
      maintainAspectRatio: false,
      plugins: {
        legend: {
          display: false,
        },
      },
      scales: {
        radar: {
          grid: {
            color: getStyle('--cui-border-color-translucent'),
            drawOnChartArea: false,
          },
          ticks: {
            color: getStyle('--cui-body-color'),
          },
        },
      },
      elements: {
        line: {
          tension: 0.4,
        },
        point: {
          radius: 0,
          hitRadius: 10,
          hoverRadius: 4,
          hoverBorderWidth: 3,
        },
      },
    }

    onMounted(() => {
      document.documentElement.addEventListener('ColorSchemeChange', () => {
        if (mainChartRef.value) {
          mainChartRef.value.chart,
            (options.scales.radar.grid.borderColor = getStyle(
              '--cui-border-color-translucent',
            ))
          mainChartRef.value.chart,
            (options.scales.radar.grid.color = getStyle(
              '--cui-border-color-translucent',
            ))
          mainChartRef.value.chart,
            (options.scales.radar.ticks.color = getStyle('--cui-body-color'))
          mainChartRef.value.chart.update()
        }
      })
    })

    return {
      data,
      mainChartRef,
      options,
    }
  },
}
</script>
