<script>
  import { navigate } from "svelte-routing";

  let username = '';
  let email = '';
  let password = '';

  function handleSubmit() {
    if (username.trim().length === 0 || username.includes(' ')) {
      alert("El nombre no debe contener espacios.");
      return;
    }

    if (!email.includes('@')) {
      alert("Por favor, introduce un correo electrónico válido.");
      return;
    }

    if (password.trim().length === 0) {
      alert("La contraseña no puede estar vacía.");
      return;
    }

    console.log('Creando cuenta:', { username, email, password });
    navigate("/windows"); // Navega a la página principal después del registro
  }

  function handleLogin(e) {
    e.preventDefault();
    navigate("/Ingresarcuenta"); // Navega a la página de login cuando el usuario hace click en "Log in"
  }
</script>

<div class="container">
  <div class="content">
    <img src="/logo.png" alt="MagicalTunes Logo" class="logo" />
    <h1>MagicalTunes</h1>

    <form on:submit|preventDefault={handleSubmit}>
      <input
        type="text"
        bind:value={username}
        placeholder="Username"
        required
      />
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
      
      <button type="submit" class="create-button">Crear</button>
    </form>

    <div class="login-link">
      ¿Tienes una cuenta? 
      <a href="/Ingresarcuenta" on:click={handleLogin}>Log in</a> <!-- Fixed href to prevent default navigation -->
    </div>
  </div>
</div>



<style>
  .container {
    min-height: 100vh;
    background-color: #1a1e21;
    color: white;
    padding: 20px;
    position: relative;
  }

  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 60px;
  }

  .logo {
    width: 120px;
    height: 120px;
    margin-bottom: 20px;
  }

  h1 {
    font-size: 2rem;
    margin-bottom: 40px;
  }

  form {
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

  .create-button {
    background-color: #b624ff;
    color: white;
    border: none;
    padding: 12px;
    border-radius: 25px;
    font-size: 1rem;
    cursor: pointer;
    margin-top: 8px;
  }

  .create-button:hover {
    background-color: #a020f0;
  }

  .login-link {
    margin-top: 20px;
    font-size: 0.9rem;
  }

  .login-link a {
    color: #ff0000;
    text-decoration: none;
    margin-left: 4px;
  }

  .login-link a:hover {
    text-decoration: underline;
  }
</style>
