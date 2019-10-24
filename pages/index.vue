<script>
import {
  createComponent,
  reactive,
  onMounted,
  SetupContext
} from '@vue/composition-api'
// import Chart from '@/components/Chart.vue'
// import VueCharts from 'vue-chartjs'
import { Bar, Line } from 'vue-chartjs'

export default createComponent({
  extends: Line,
  // setup(props, context) {
  //   const emitSample = () => {
  //     context.emit('emit-sample', 'サンプル')
  //   }
  //   const state = reactive({
  //     test: context
  //   })
  //   onMounted(() => {
  //     console.log(context)
  //     // context.renderChart({
  //     //   labels: [
  //     //     'January',
  //     //     'February',
  //     //     'March',
  //     //     'April',
  //     //     'May',
  //     //     'June',
  //     //     'July'
  //     //   ],
  //     //   datasets: [
  //     //     {
  //     //       label: 'Data One',
  //     //       backgroundColor: '#f87979',
  //     //       data: [40, 39, 10, 40, 39, 80, 40]
  //     //     }
  //     //   ]
  //     // })
  //   })
  //   return {
  //     state
  //   }
  // }
  setup(props, context) {
    console.log(context)
  },
  mounted() {
    console.log(this)
    this.renderChart({
      labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
      datasets: [
        {
          label: 'Data One',
          backgroundColor: '#f87979',
          data: [40, 39, 10, 40, 39, 80, 40]
        }
      ]
    })
  }
})
</script>
