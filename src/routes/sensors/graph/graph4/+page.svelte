<script>
  import { onMount } from 'svelte';
  import { Chart, registerables } from 'chart.js';

  let chartCanvas;
  Chart.register(...registerables);

  onMount(() => {
    new Chart(chartCanvas, {
      type: 'pie',
      data: {
        labels: ['赤', '青', '黄', '緑', '紫', '橙'],
        datasets: [{
          label: 'サンプルデータ',
          data: [12, 19, 3, 5, 2, 3],
          backgroundColor: [
            'rgba(255, 99, 132, 0.6)',
            'rgba(54, 162, 235, 0.6)',
            'rgba(255, 206, 86, 0.6)',
            'rgba(75, 192, 192, 0.6)',
            'rgba(153, 102, 255, 0.6)',
            'rgba(255, 159, 64, 0.6)'
          ],
          borderColor: 'rgba(255, 255, 255, 1)',
          borderWidth: 1
        }]
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
          legend: {
            position: 'bottom' // ← 下に寄せて圧迫を防ぐ
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
    display: block;
    width: 100% !important;
    height: 100% !important;
  }
</style>

<div class="chart-container">
  <canvas bind:this={chartCanvas}></canvas>
</div>
