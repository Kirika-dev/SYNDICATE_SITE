<script>
  export let title;
  export let status; // 'active', 'inactive', 'soon'
  export let description;
  export let image;
  export let link;
</script>

<div class="card">
  <div class="badge {status}">
    {status === 'active' ? 'Актуально' : status === 'soon' ? 'Скоро неактуально' : 'Неактуально'}
  </div>
  <img class="bg" src={image} alt={title} />
  <div class="info">
    <h3>{title}</h3>
    <p>{description}</p>
    <a class="join-button" href={link} target="_blank" rel="noopener noreferrer">
      Присоединиться
    </a>
  </div>
</div>

<style>
  .card {
    position: relative;
    background: #111;
    border: 1px solid #333;
    border-radius: 12px;
    overflow: hidden;
    width: 320px;
    display: flex;
    flex-direction: column;
    box-shadow: 0 0 12px #0006;
    transition: transform 0.2s;
  }

  .card:hover {
    transform: scale(1.02);
  }

  .bg {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }

  .badge {
    position: absolute;
    top: 10px;
    left: 10px;
    background: gray;
    color: white;
    font-size: 0.75rem;
    padding: 0.2rem 0.6rem;
    border-radius: 6px;
    font-weight: bold;
    z-index: 1;
  }

  .badge.active {
    background: green;
  }

  .badge.soon {
    background: orange;
  }

  .badge.inactive {
    background: #666;
  }

  .info {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
  }

  h3 {
    margin: 0 0 0.5rem;
  }

  p {
    flex-grow: 1;
    font-size: 0.85rem;
    color: #aaa;
  }

  .join-button {
    margin-top: 1rem;
    padding: 0.5rem 1rem;
    background: rgb(100, 85, 65);
    color: white;
    border: none;
    border-radius: 6px;
    text-align: center;
    text-decoration: none;
    font-weight: bold;
    transition: background 0.3s;
  }

  .join-button:hover {
    background: rgb(120, 100, 80);
  }
</style>
