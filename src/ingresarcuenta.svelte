<script>
  import { navigate } from "svelte-routing";

  let email = '';
  let password = '';

  function handleLogin(e) {
    e.preventDefault();
    console.log('Login attempt:', { email, password });
    navigate("/windows"); // Navega a la página principal después del login
  }

  function handleBack() {
    window.history.back(); // Vuelve a la pantalla anterior
  }
</script>

<div class="login-container">
  <button class="back-button" on:click={handleBack}>
    <svg xmlns="/Ingresarcuenta" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M19 12H5M12 19l-7-7 7-7"/>
    </svg>
  </button>

  <main class="login-content">
    <img src="/logo.png" alt="MagicalTunes" class="logo" />
    <h1>MagicalTunes</h1>

    <form on:submit={handleLogin} class="login-form">
      <input
        type="email"
        bind:value={email}
        placeholder="Email"
        required
      />
      <input
        type="password"
        bind:value={password}
        placeholder="Password"
        required
      />
      <button type="submit">Ingresar</button>
    </form>
  </main>
</div>



<style>
  .login-container {
    background-color: #1a1e21;
    min-height: 100vh;
    color: white;
    position: relative;
    padding: 20px;
  }

  .back-button {
    position: absolute;
    top: 20px;
    left: 20px;
    background: none;
    border: none;
    color: white;
    cursor: pointer;
    padding: 8px;
  }

  .login-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    padding: 20px;
    gap: 24px;
  }

  .logo {
    width: 120px;
    height: 120px;
    margin-bottom: 8px;
  }

  h1 {
    font-size: 2rem;
    margin: 0;
  }

  .login-form {
    display: flex;
    flex-direction: column;
    width: 100%;
    max-width: 320px;
    gap: 16px;
  }

  input {
    width: 100%;
    padding: 12px;
    border-radius: 25px;
    background-color: transparent;
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: white;
    font-size: 1rem;
  }

  input::placeholder {
    color: rgba(255, 255, 255, 0.5);
  }

  button[type="submit"] {
    background-color: #b624ff;
    color: white;
    border: none;
    padding: 12px;
    border-radius: 25px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.2s;
  }

  button[type="submit"]:hover {
    background-color: #a020f0;
  }

  @media (max-width: 768px) {
    .login-content {
      padding-top: 60px;
    }
  }
</style>
