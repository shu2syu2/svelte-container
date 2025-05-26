<script>
  const iframeUrl = '/sensors';
</script>

<style>
  :global(html), :global(body) {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow: hidden;
  }

  .container {
    display: flex;
    height: 100vh;
    overflow: hidden;
  }

  .menu {
    width: 15%;
    padding: 1rem;
    background-color: #f0f0f0;
  }

  .main {
    width: 85%;
    height: 100%;
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
      <li><a href="/sensors">センサー画面</a></li>
    </ul>
  </div>
  <div class="main">
    <iframe src={iframeUrl}></iframe>
  </div>
</div>
