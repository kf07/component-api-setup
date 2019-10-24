<!--<script>-->
<!--import { reactive, createComponent, onMounted } from '@vue/composition-api'-->
<!--import { Bar } from 'vue-chartjs'-->
<!--export default createComponent({-->
<!--  extends: Bar,-->
<!--  props: ['data', 'options'],-->
<!--  name: 'chart',-->
<!--  setup(props) {-->
<!--    onMounted(() => {-->
<!--      this.renderChart(props.data, props.options)-->
<!--    })-->
<!--  }-->
<!--})-->
<!--</script>-->

<!--<style scoped></style>-->
<script>
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  props: ['chartdata', 'options'],
  mounted() {
    this.renderChart(this.chartdata, this.options)
  }
}
</script>

<style></style>
