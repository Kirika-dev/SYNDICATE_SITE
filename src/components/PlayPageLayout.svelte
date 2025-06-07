<section class="intro">...</section>
<section class="game-list">
  <GameCard game={onceHuman} />
  <GameCard game={gta5rp} />
  <GameCard game={anotherGame} />
</section>
<script lang="ts">
  import GameCard from "../lib/components/GameCard.svelte";

  interface Game {
    name: string;
    image: string;
    description: string;
    discord: string;
    steam:string;
    launcher?: string;
    active?: boolean;
  }

  const onceHuman: Game = {
    name: "Once Human",
    image: "/images/once-human.jpg",