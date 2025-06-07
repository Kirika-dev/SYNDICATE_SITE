<!-- src/lib/components/OnceHumanSection.svelte -->
<script>
  const discordInvite = "https://discord.gg/7Gus6wKN";
  const steamLink = "https://store.steampowered.com/app/2139460/Once_Human/";
</script>

<section class="relative h-screen w-full overflow-hidden bg-black text-white">
  <video autoplay muted loop playsinline class="absolute inset-0 h-full w-full object-cover opacity-20">
    <source src="/assets/once-human-trailer.mp4" type="video/mp4" />
  </video>

  <div class="relative z-10 flex flex-col items-center justify-center h-full text-center px-4 backdrop-blur-sm">
    <h1 class="text-4xl md:text-6xl font-bold mb-4">Мы играем в Once Human</h1>
    <p class="text-lg md:text-xl mb-6 max-w-xl">
      Присоединяйся к нам в выживании среди безумия. Наш улей — Wagner, регион — Красные Пески.
    </p>

    <div class="flex flex-col sm:flex-row gap-4">
      <a href={steamLink} target="_blank" class="bg-blue-600 hover:bg-blue-700 px-6 py-3 rounded-xl shadow-lg text-white">Скачать игру</a>
      <a href="#how-to-join" class="bg-white text-black hover:bg-gray-200 px-6 py-3 rounded-xl shadow-lg">Как начать играть</a>
      <a href={discordInvite} target="_blank" class="bg-pink-600 hover:bg-pink-700 px-6 py-3 rounded-xl shadow-lg text-white">Наш Discord</a>
    </div>
  </div>
</section>

<section id="how-to-join" class="bg-[#111] text-white py-20 px-6 md:px-20">
  <h2 class="text-3xl md:text-4xl font-bold text-center mb-10">Как начать играть с нами</h2>
  <div class="grid md:grid-cols-5 gap-8 text-center">
    <div>
      <p class="text-5xl mb-4">1️⃣</p>
      <p>Скачай Once Human в Steam</p>
    </div>
    <div>
      <p class="text-5xl mb-4">2️⃣</p>
      <p>Создай персонажа и пройди обучение</p>
    </div>
    <div>
      <p class="text-5xl mb-4">3️⃣</p>
      <p>Открой карту и найди Красные Пески</p>
    </div>
    <div>
      <p class="text-5xl mb-4">4️⃣</p>
      <p>Найди улей Wagner — там наша база</p>
    </div>
    <div>
      <p class="text-5xl mb-4">5️⃣</p>
      <p>Вступи в наш Discord и начни выживание</p>
    </div>
  </div>
</section>
