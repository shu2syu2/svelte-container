<script>
  const graph1 = '/sensors/graph/graph1';
  const graph2 = '/sensors/graph/graph2';
  const graph3 = '/sensors/graph/graph3';
  const graph4 = '/sensors/graph/graph4';
</script>

<style>
  :global(html), :global(body) {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow: hidden;
    font-size: 16px;
  }

  .container {
    display: flex;
    height: 100vh;
    overflow: hidden;
  }

  .menu {
    width: 15%;
    padding: 1rem;
    background-color: #eee;
    overflow-y: auto;
  }

  .main {
    width: 85%;
    display: flex;
    flex-direction: column;
    height: 100%;
    overflow: hidden;
  }

  .row.title {
    height: 7%;
    flex-shrink: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ccc;
    font-size: 1.5rem;
  }

  .row.graphs:nth-of-type(2) {
    height: 43%;
  }

  .row.graphs:nth-of-type(3) {
    height: 50%;
  }

  .row.graphs {
    display: flex;
    overflow: hidden;
  }

  .column {
    width: 50%;
    height: 100%;
    overflow: hidden;
  }

  iframe {
    width: 100%;
    height: 100%;
    border: none;
    display: block;
  }
</style>

<div class="container">
  <div class="menu">
    <h2>メニュー</h2>
    <ul>
      <li><a href="/">トップへ</a></li>
    </ul>
  </div>

  <div class="main">
    <div class="row title">
      <div>センサーグラフ表示</div>
    </div>
    <div class="row graphs">
      <div class="column"><iframe src={graph1}></iframe></div>
      <div class="column"><iframe src={graph2}></iframe></div>
    </div>
    <div class="row graphs">
      <div class="column"><iframe src={graph3}></iframe></div>
      <div class="column"><iframe src={graph4}></iframe></div>
    </div>
  </div>
</div>
