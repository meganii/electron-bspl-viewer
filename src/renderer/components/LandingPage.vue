<template>
  <div>
    <input class="input" v-model="asset" placeholder="資産名">
    <input class="input" v-model="name" placeholder="項目名"> 
    <input class="input" v-model="value" placeholder="金額">

    <p class="name">資産名: {{ asset }}</p>
    <p class="name">項目名: {{ name }}</p>
    <p class="name">金額: {{ value }}</p>

    <ul id="example-1">
      <li v-for="data in chartData.datasets" :key="data.label">
        {{ data.label }}
      </li>
    </ul>

    <stacked-bar :width="900" :height="300" :chartData="chartData" :options="options" />
    <button @click="load">load</button>
  </div>
</template>

<script>
import StackedBar from './LandingPage/StackedBar'
export default {
  components: {
    StackedBar
  },
  data () {
    return {
      asset: '',
      name: '',
      value: '',
      chartData: {},
      options: {
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
      }
    }
  },
  methods: {
    load: function () {
      console.log('load')
      this.chartData = {
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
      }
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body { font-family: 'Source Sans Pro', sans-serif; }

  #wrapper {
    background:
      radial-gradient(
        ellipse at top left,
        rgba(255, 255, 255, 1) 40%,
        rgba(229, 229, 229, .9) 100%
      );
    height: 100vh;
    padding: 60px 80px;
    width: 100vw;
  }

  #logo {
    height: auto;
    margin-bottom: 20px;
    width: 420px;
  }

  main {
    display: flex;
    justify-content: space-between;
  }

  main > div { flex-basis: 50%; }

  .left-side {
    display: flex;
    flex-direction: column;
  }

  .welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
  }

  .title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: black;
    margin-bottom: 10px;
  }

  .doc button {
    font-size: .8em;
    cursor: pointer;
    outline: none;
    padding: 0.75em 2em;
    border-radius: 2em;
    display: inline-block;
    color: #fff;
    background-color: #4fc08d;
    transition: all 0.15s ease;
    box-sizing: border-box;
    border: 1px solid #4fc08d;
  }

  .doc button.alt {
    color: #42b983;
    background-color: transparent;
  }
</style>
