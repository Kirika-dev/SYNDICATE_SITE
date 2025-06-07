<script>
  export let stream;
</script>

<a href={stream.url} target="_blank" rel="noopener noreferrer" class="stream-card">
  <img class="stream-thumb" src={stream.thumbnail} alt={`Thumbnail ${stream.streamer}`} />
  <div class="stream-info">
    <div class="stream-title">{stream.streamer} — {stream.title}</div>
    <div class="stream-details">
      Платформа: {stream.platform} | Зрителей: {stream.viewers}
      <span class="live-badge">LIVE</span>
    </div>
  </div>
</a>

<style>
  .stream-card {
    background: #111;
    border: 1px solid #333;
    border-radius: 8px;
    overflow: hidden;
    width: 320px;
    cursor: pointer;
    transition: border-color 0.3s;
    text-decoration: none;
    color: inherit;
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
  .live-badge {
    display: inline-block;
    background: red;
    color: white;
    padding: 0.1rem 0.5rem;
    font-size: 0.75rem;
    font-weight: bold;
    border-radius: 3px;
    margin-left: 0.5rem;
  }
</style>