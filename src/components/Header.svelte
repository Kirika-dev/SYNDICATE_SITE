<script>
  const logoUrl = '/logo-placeholder.png';
</script>

<header>
  <img src={logoUrl} alt="SYNDICATE Logo" class="logo" />
  <nav>
    <a href="#schedule">Расписание</a>
    <a href="#news">Новости</a>
    <a href="#gallery">Галерея</a>
    <a href="#forum">Форум</a>
    <a href="#chat">Чат</a>
  </nav>
</header>

<style>
  header {
    display: flex;
    align-items: center;
    padding: 1rem 2rem;
    border-bottom: 1px solid #222;
  }
  .logo {
    height: 50px;
    width: auto;
    margin-right: 2rem; /* Adjust as needed */
    transition: transform 0.3s;
  }
  nav a {
    margin-left: 1.5rem;
    color: #bbb;
    text-decoration: none;
    font-weight: 600;
    transition: color 0.3s;
  }
  nav a:hover {
    color: var(--accent);
  }
</style>