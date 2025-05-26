<script>
  import { onMount } from 'svelte';
  import { Chart, registerables } from 'chart.js';

  let chartCanvas;
  let chart;

  Chart.register(...registerables);

  onMount(() => {
    if (chart) chart.destroy();

    chart = new Chart(chartCanvas, {
      type: 'bar',
      data: {
        datasets: [{
          label: '散布図データ',
          data: [
            { x: 1, y: 3 },
            { x: 2, y: 5 },
            { x: 3, y: 2 },
            { x: 4, y: 8 },
            { x: 5, y: 6 }
          ],
          backgroundColor: 'rgba(255, 99, 132, 0.7)'
        }]
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          x: {
            type: 'linear',
            position: 'bottom',
            title: { display: true, text: 'X 軸' }
          },
          y: {
            title: { display: true, text: 'Y 軸' }
          }
        }
      }
    });
  });
</script>

<style>
  :global(html), :global(body) {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow: hidden;
  }

  .chart-container {
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
  }

  canvas {
    width: 100% !important;
    height: 100% !important;
    display: block;
  }
</style>

<div class="chart-container">
  <canvas bind:this={chartCanvas}></canvas>
</div>
