<script>
import { Bar } from 'vue-chartjs'
export default {
  extends: Bar,
  mounted () {
    this.renderChart({
      labels: ['Day1', 'Day2', 'Day3'],
      datasets: [
        {
          label: 'base data',
          data: [ 27, 33, 49 ],
          borderColor: '#333',
          backgroundColor: '#333'
        },
        {
          label: 'stacked data',
          data: [ 10, 15, 22 ],
          borderColor: '#666',
          backgroundColor: '#666'
        }
      ]
    },
    {
      responsive: false,
      scales: {
        xAxes: [{
          stacked: true
        }],
        yAxes: [{
          stacked: true,
          ticks: {
            beginAtZero: true,
            min: 0
          }
        }]
      }
    })
  }
}
</script>