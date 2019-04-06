<template>
  <div id="app">
    <h1>chart.js</h1>
    <canvas id="myChart" width="200" height="200"></canvas>
  </div>
</template>
<script>
// NOTE 아래의 chart.js는 package.json에 적혀있는 이름과 같아야 한다.
// REVIEW 내가 외부 라이브러리를 -D로 설치했더니 import가 안됐어서 다시 지우고 --save로 저장했더니 import 됨!!!!
import Chart from 'chart.js';

export default {
  mounted() {
    const ctx = document.getElementById('myChart').getContext('2d');
    const myChart = new Chart(ctx, {
      type: 'bar',
      data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
          label: '# of Votes',
          data: [12, 19, 3, 5, 2, 3],
          backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(255, 206, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(255, 159, 64, 0.2)',
          ],
          borderColor: [
            'rgba(255, 99, 132, 1)',
            'rgba(54, 162, 235, 1)',
            'rgba(255, 206, 86, 1)',
            'rgba(75, 192, 192, 1)',
            'rgba(153, 102, 255, 1)',
            'rgba(255, 159, 64, 1)',
          ],
          borderWidth: 1,
        }],
      },
      options: {
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true,
            },
          }],
        },
      },
    });
  },
};
</script>
<style lang="scss">
</style>
