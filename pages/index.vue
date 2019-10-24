<script>
import { createComponent, reactive } from '@vue/composition-api'
// import Chart from '@/components/Chart.vue'
import { Line } from 'vue-chartjs'

export default createComponent({
  extends: Line,
  mounted() {
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
