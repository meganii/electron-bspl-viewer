<script>
import { Bar } from 'vue-chartjs'
export default {
  extends: Bar,
  mounted () {
    this.renderChart({
      labels: ['B/S', 'P/L'],
      datasets: [
        {
          label: '固定資産',
          data: [ 27, null ],
          borderColor: '#333',
          backgroundColor: '#333',
          stack: 'stack0'
        },
        {
          label: '流動資産',
          data: [ 10, null ],
          borderColor: '#666',
          backgroundColor: '#666',
          stack: 'stack0'
        },
        {
          label: '純資産',
          data: [ 17, null ],
          borderColor: '#333',
          backgroundColor: '#333',
          stack: 'stack1'
        },
        {
          label: '負債',
          data: [ 20, null ],
          borderColor: '#666',
          backgroundColor: '#666',
          stack: 'stack1'
        },
        {
          label: '営業利益',
          data: [ null, 10 ],
          borderColor: '#666',
          backgroundColor: '#666',
          stack: 'stack0'
        },
        {
          label: '販管費',
          data: [ null, 10 ],
          borderColor: '#444',
          backgroundColor: '#444',
          stack: 'stack0'
        },
        {
          label: '売上原価',
          data: [ null, 80 ],
          borderColor: '#333',
          backgroundColor: '#333',
          stack: 'stack0'
        },
        {
          label: '売上',
          data: [ null, 100 ],
          borderColor: '#666',
          backgroundColor: '#666',
          stack: 'stack1'
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