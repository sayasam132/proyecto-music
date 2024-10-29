<script>

    let phoneNumber = '';
  
    function handleSignUp() {
      // Lógica para manejar el registro
      console.log('Registrando con número de teléfono:', phoneNumber);
    }
  
    function handleGoogleSignIn() {
      // Lógica para iniciar sesión con Google
      console.log('Iniciando sesión con Google');
    }
  
    function handleFacebookSignIn() {
      // Lógica para iniciar sesión con Facebook
      console.log('Iniciando sesión con Facebook');
    }
  </script>
  
  <main>
    <div class="container">
      <img src="/logo.png" alt="Logo" class="logo" />
      <h1> Create your account</h1>
      <button class="sign-up-btn" on:click={handleSignUp}>Sign up free</button>
      <input
        type="tel"
        bind:value={phoneNumber}
        placeholder="Número de teléfono"
        class="phone-input"
      />
      <button class="google-btn" on:click={handleGoogleSignIn}>
        <img src="/google.png" alt="Google icon" />
        Continuar con Google
      </button>
      <button class="facebook-btn" on:click={handleFacebookSignIn}>
        <img src="/facebook.png" alt="Facebook icon"/>
        Continuar con Facebook
      </button>
      <a href="/login" class="login-link">Log in</a>
    </div>
  </main>
  
  <style>
    main {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #1a1e21;
      color: white;
      font-family: Arial, sans-serif;
    }
  
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 300px;
    }
  
    .logo {
      width: 100px;
      height: 100px;
      margin-bottom: 20px;
    }
  
    h1 {
      margin-bottom: 20px;
    }
  
    .sign-up-btn {
      background-color: #1db954;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 20px;
      margin-bottom: 20px;
      cursor: pointer;
    }
  
        .phone-input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #333;
    background-color: transparent;
    color: white;
    text-align: center; /* Centra el texto del input */
    }

  
    .google-btn, .facebook-btn {
      width: 100%;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 5px;
      border: 1px solid #333;
      background-color: transparent;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
  
    .google-btn img, .facebook-btn img {
      margin-right: 10px;
      width: 20px;
      height: 20px;
    }
  
    .login-link {
      color: white;
      text-decoration: none;
    }
  </style>