<script>
  import StreamCard from './StreamCard.svelte';

  let streams = [
    {
      id: 'twitch1',
      platform: 'Twitch',
      streamer: 'Morttemia_TTV',
      title: 'Играем в GTA 5 RP',
      viewers: 420,
      url: 'https://www.twitch.tv/morttemia_ttv',
      thumbnail: 'https://static-cdn.jtvnw.net/previews-ttv/live_user_morttemia_ttv-320x180.jpg',
      isLive: true,
    },
    {
      id: 'youtube1',
      platform: 'YouTube',
      streamer: 'StreamerTwo',
      title: 'Стрим по Fortnite',
      viewers: 210,
      url: 'https://www.youtube.com/watch?v=example',
      thumbnail: 'https://i.ytimg.com/vi/example/hqdefault.jpg',
      isLive: true,
    }
  ];
</script>

<section id="live-streams">
  <h2>Сейчас в эфире</h2>
  <div class="streams">
    {#each streams.filter(s => s.isLive) as stream}
      <StreamCard {stream} />
    {/each}
    {#if streams.filter(s => s.isLive).length === 0}
      <p>Никто не в эфире сейчас.</p>
    {/if}
  </div>
</section>

<style>
  .streams {
    display: flex;
    gap: 1.5rem;
    flex-wrap: wrap;
    margin-top: 2rem;
  }
</style>