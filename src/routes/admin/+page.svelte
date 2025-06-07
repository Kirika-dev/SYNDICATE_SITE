<script>
  import games from '$lib/data/games.json';
  import { onMount } from 'svelte';

  let selectedGame = null;
  let form = {
    title: '',
    description: '',
    image: '',
    link: '',
    active: true
  };

  function editGame(index) {
    selectedGame = index;
    Object.assign(form, games[index]);
  }

  function updateGame() {
    if (selectedGame !== null) {
      games[selectedGame] = { ...form };
    }
  }

  function addGame() {
    games.push({ ...form });
    resetForm();
  }

  function resetForm() {
    form = {
      title: '',
      description: '',
      image: '',
      link: '',
      active: true
    };
    selectedGame = null;
  }

  function exportJSON() {
    const blob = new Blob([JSON.stringify(games, null, 2)], {
      type: 'application/json',
    });
    const url = URL.createObjectURL(blob);

    const link = document.createElement('a');
    link.href = url;
    link.download = 'games.json';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);

    URL.revokeObjectURL(url);
  }
</script>

<!-- Оставляем тот же стиль и HTML как раньше -->

<main>
  <h1>Редактор карточек игр</h1>

  <div class="game-list">
    {#each games as game, i}
      <div class="game-item" on:click={() => editGame(i)}>
        {game.title}
      </div>
    {/each}
  </div>

  <h2>{selectedGame === null ? 'Новая игра' : 'Редактировать игру'}</h2>

  <input bind:value={form.title} placeholder="Название игры" />
  <textarea bind:value={form.description} placeholder="Описание"></textarea>
  <input bind:value={form.image} placeholder="Ссылка на изображение" />
  <input bind:value={form.link} placeholder="Ссылка на игру/дискорд" />
  <label>
    <input type="checkbox" bind:checked={form.active} />
    Игра активна
  </label>
  <br />
  <button on:click={selectedGame === null ? addGame : updateGame}>
    {selectedGame === null ? 'Добавить' : 'Сохранить'}
  </button>
  <button on:click={resetForm}>Очистить</button>

  <hr style="margin: 2rem 0;" />

  <button on:click={exportJSON}>📦 Скачать JSON</button>
</main>
