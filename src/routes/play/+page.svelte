<script>
  import GameCard from '../../lib/components/GameCard.svelte';

  const games = [
    {
      title: 'Once Human',
      status: 'active',
      description: 'Manibus-X0176, Мир-2, Улей Wagner, регион Красные Пески',
      image: '/games/once-human.png',
      link: 'https://discord.gg/7Gus6wKN'
    },
    {
      title: 'GTA 5 — Paradise RP',
      status: 'soon',
      description: 'Сервер Paradise RP, фракция SANG, лидерка. Скоро не будет актуально.',
      image: '/assets/gta5.jpg',
      link: 'https://paradise-rp.ru'
    }
  ];
</script>

<style>
  .game-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2rem;
    padding: 2rem;
  }
</style>

<h1 class="text-center text-3xl mb-6">Как играть с нами</h1>

<div class="game-grid">
  {#each games as game}
    <GameCard {...game} />
  {/each}
</div>
