<script>
  const accentColor = 'rgb(100, 85, 65)';

  const streams = [
    {
      id: 'twitch1',
      platform: 'Twitch',
      streamer: 'Morttemia',
      title: 'Выживаем в Once Human',
      viewers: 420,
      url: 'https://www.twitch.tv/morttemia_ttv',
      thumbnail: 'https://static-cdn.jtvnw.net/previews-ttv/live_user_morttemia_ttv-320x180.jpg',
      isLive: true,
    },
  ];
</script>

<style>
  :global(body) {
    margin: 0;
    background-color: #000;
    color: #fff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  
  
   .video-bg {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    z-index: -1;
  }


  .overlay {
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: rgba(0, 0, 0, 0.6);
    z-index: 0;
  }
  header > * {
    z-index: 1;
  }
  .logo {
    height: 100px;
    margin-bottom: 1rem;
  }
  h1 {
    font-size: 3rem;
    margin: 0;
  }
  .cta-button {
    background-color: var(--accent);
    color: white;
    padding: 0.75rem 1.5rem;
    font-size: 1.1rem;
    font-weight: bold;
    border: none;
    border-radius: 0.5rem;
    margin-top: 2rem;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  .cta-button:hover {
    background-color: rgb(120, 100, 70);
  }
  section {
    padding: 4rem 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }
  .streams {
    display: flex;
    gap: 2rem;
    flex-wrap: wrap;
    justify-content: center;
  }
  .stream-card {
    background: #111;
    border: 1px solid #333;
    border-radius: 8px;
    overflow: hidden;
    width: 320px;
    cursor: pointer;
    transition: border-color 0.3s;
  }
  .stream-card:hover {
    border-color: var(--accent);
  }
  .stream-thumb {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }
  .stream-info {
    padding: 0.8rem 1rem;
  }
  .stream-title {
    font-weight: 700;
    color: #ddd;
  }
  .stream-details {
    font-size: 0.85rem;
    color: #aaa;
    margin-top: 0.2rem;
  }
  footer {
    text-align: center;
    padding: 2rem;
    background: #111;
    color: #666;
    font-size: 0.9rem;
  }
</style>

<svelte:head>
  <style>
    :root {
      --accent: {accentColor};
    }
  </style>
</svelte:head>

<header>
  <div class="overlay"></div>
  <img src="/logo-placeholder.png" alt="SYNDICATE Logo" class="logo" />
  <h1>Добро пожаловать в SYNDICATE</h1>
  <a href="/play">
    <button class="cta-button">Как играть с нами</button>
  </a>
</header>
<video class="video-bg" autoplay muted loop playsinline>
  <source src="/video/once-human-trailer.mp4" type="video/mp4" />
  Ваш браузер не поддерживает видеофон.
</video>
<section id="live-streams">
  <h2>Сейчас в эфире</h2>
  <div class="streams">
    {#each streams as stream (stream.id)}
      {#if stream.isLive}
        <a href={stream.url} target="_blank" rel="noopener noreferrer" class="stream-card">
          <img class="stream-thumb" src={stream.thumbnail} alt={`Thumbnail ${stream.streamer}`} />
          <div class="stream-info">
            <div class="stream-title">{stream.streamer} — {stream.title}</div>
            <div class="stream-details">
              Платформа: {stream.platform} | Зрителей: {stream.viewers}
            </div>
          </div>
        </a>
      {/if}
    {/each}
  </div>
</section>

<section id="about">
  <h2>О нас</h2>
  <p>Мы — объединение стримеров, контент-мейкеров и игроков. Играем в актуальные проекты, ведем трансляции и собираем комьюнити.</p>
</section>

<footer>
  © 2025 SYNDICATE. Все права защищены.
</footer>
