<template>
  <div>
    <h1>New Page</h1>
    <p>This is the content of the new page.</p>
  </div>
  <div>
    <MainChart style="height: 400px; max-height: 400px; margin-top: 40px" />
    </div>
</template>

<script>
import MainChart from './MainChart'
import WidgetsStatsA from './../widgets/WidgetsStatsTypeA.vue'
import WidgetsStatsD from './../widgets/WidgetsStatsTypeD.vue'

export default {
  name: 'insightsFilter',
  components: {
    MainChart,
    WidgetsStatsA,
    WidgetsStatsD,
  },
  setup() {
    const progressGroupExample1 = [
      { title: 'Shots', value1: 34, value2: 78 },
      { title: 'Interceptions', value1: 56, value2: 94 },
      { title: 'Successful Tackles', value1: 12, value2: 67 },
      { title: 'Progressive Passes', value1: 43, value2: 91 },
      { title: 'Minutes PLayed', value1: 22, value2: 73 },
      { title: 'Chances Created', value1: 53, value2: 82 },
      { title: 'Touches', value1: 9, value2: 69 },
    ]
    return {
      progressGroupExample1,
    }
  }
}
</script>
