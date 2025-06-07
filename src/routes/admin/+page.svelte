<script>
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';

  let games = writable([]);

  onMount(async () => {
    const res = await fetch('/games.json');
    const data = await res.json();
    games.set(data);
  });

  function addGame() {
    games.update(list => [...list, {
      title: '',
      server: '',
      description: '',
      link: '',
      status: 'актуальна',
      image: ''
    }]);
  }

  function deleteGame(index) {
    games.update(list => {
      list.splice(index, 1);
      return list;
    });
  }

  function saveChanges() {
    games.subscribe(value => {
      console.log('Сохранить в JSON:', JSON.stringify(value, null, 2));
      alert("Сохранено (в консоль)");
    })();
  }
</script>

<h1 class="text-2xl font-bold mb-4">Редактор игр</h1>

<button class="bg-blue-600 text-white px-4 py-2 rounded mb-4" on:click={addGame}>➕ Добавить игру</button>

{#each $games as game, index}
  <div class="border p-4 rounded mb-4 space-y-2 bg-gray-50">
    <input class="w-full p-2 border" bind:value={game.title} placeholder="Название" />
    <input class="w-full p-2 border" bind:value={game.server} placeholder="Сервер / Улей" />
    <input class="w-full p-2 border" bind:value={game.status} placeholder="Статус (актуальна / неактуальна)" />
    <textarea class="w-full p-2 border" bind:value={game.description} placeholder="Описание" />
    <input class="w-full p-2 border" bind:value={game.link} placeholder="Ссылка на сайт / Discord" />
    <input class="w-full p-2 border" bind:value={game.image} placeholder="URL картинки" />
    <button class="bg-red-500 text-white px-3 py-1 rounded" on:click={() => deleteGame(index)}>❌ Удалить</button>
  </div>
{/each}

<button class="bg-green-600 text-white px-4 py-2 rounded mt-4" on:click={saveChanges}>💾 Сохранить</button>
