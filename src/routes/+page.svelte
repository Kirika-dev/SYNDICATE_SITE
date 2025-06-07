<script>
  import Header from '../components/Header.svelte';
  import LiveStreams from '../components/LiveStreams.svelte';
  import OnceHumanSection from '../components/OnceHumanSection.svelte';
    //import StreamPanel from "$components/StreamPanel.svelte"; // если ты сделал такой компонент
  import { goto } from "$app/navigation";
  </script>

<Header />
<main>
  <h1>Добро пожаловать в SYNDICATE</h1>
  <p>Объединение стримеров, геймеров и контент-мейкеров.</p>

  <LiveStreams />
<section class="relative min-h-screen w-full bg-black text-white flex flex-col items-center justify-center px-4">


  <div class="z-10 max-w-3xl text-center">
    <h1 class="text-5xl font-bold mb-4 drop-shadow">Добро пожаловать в SYNDICATE</h1>
    <p class="text-xl mb-8 drop-shadow">Следи за стримами и играй с нами!</p>

    <!-- Стримы -->
    <!-- <StreamPanel /> -->

    <!-- Кнопка -->
    <button
      on:click={() => goto('/play')}
      class="mt-10 bg-indigo-600 hover:bg-indigo-700 text-white px-8 py-4 text-lg font-semibold rounded-xl shadow transition"
    >
      Как играть с нами
    </button>
  </div>
</section>
  <!--<OnceHumanSection /> -->
  <section id="schedule">
    <h2>Расписание</h2>
    <p>Скоро будет доступно.</p>
  </section>
  <section id="news">
    <h2>Новости</h2>
    <p>Следите за нашими обновлениями в Discord.</p>
  </section>
  <section id="gallery">
    <h2>Галерея</h2>
    <p>Скоро будет доступно.</p>
  </section>
  <section id="forum">
    <h2>Форум</h2>
    <p>Скоро будет доступно.</p>
  </section>
  <section id="chat">
    <h2>Чат</h2>
    <p>Присоединяйтесь к нашему Discord для общения.</p>
  </section>
  <section id="contact">
    <h2>Контакты</h2>
<p>Для сотрудничества и вопросов пишите на почту: <a href="mailto:info@syndicate.com">info@syndicate.com</a>.</p>
  </section>
</main>