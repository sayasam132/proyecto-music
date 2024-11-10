<script>
  let planDetails = {
    premium: '',
    family: ''
  };
</script>

<main>
  <button class="back-button">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="m12 19-7-7 7-7"/>
      <path d="M19 12H5"/>
    </svg>
  </button>

  <div class="content">
    <div class="logo-container">
      <div class="logo">
        <span>🎵</span>
      </div>
    </div>
    <h1>MagicalTunes</h1>

    <div class="plans">
      <div class="plan">
        <div class="plan-title premium">premium music $ 2</div>
        <div class="plan-box">
          <textarea 
            bind:value={planDetails.premium} 
            placeholder="Enter premium plan details"
          />
        </div>
        <!-- Botón para redirigir al pago del plan premium -->
        <a href="/payment?plan=premium&price=2" class="btn">Seleccionar Premium</a>
      </div>

      <div class="plan">
        <div class="plan-title family">family plan $ 5</div>
        <div class="plan-box">
          <textarea 
            bind:value={planDetails.family} 
            placeholder="Enter family plan details"
          />
        </div>
        <!-- Botón para redirigir al pago del plan familiar -->
        <a href="/payment?plan=family&price=5" class="btn">Seleccionar Family</a>
      </div>
    </div>
  </div>
</main>

<style>
  main {
    min-height: 100vh;
    background-color: #1a1d21;
    color: white;
    padding: 2rem;
    font-family: system-ui, -apple-system, sans-serif;
  }

  .back-button {
    background: none;
    border: none;
    color: white;
    cursor: pointer;
    padding: 0.5rem;
    margin-bottom: 2rem;
  }

  .content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }

  .logo-container {
    width: 100px;
    height: 100px;
    background: white;
    border-radius: 50%;
    padding: 0.5rem;
  }

  .logo {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: linear-gradient(to right, #4a90e2, #9b51e0, #e91e63);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2rem;
  }

  h1 {
    font-size: 2rem;
    font-weight: bold;
    margin: 0;
  }

  .plans {
    display: flex;
    gap: 2rem;
    width: 100%;
    padding: 3 rem;
  }

  .plan {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .plan-title {
    width: 100%;
    max-width: 200px;
    padding: 0.75rem 2rem;
    border-radius: 2rem;
    text-align: center;
    font-weight: 500;
  }

  .premium {
    background-color: #8eb6e3;
  }

  .family {
    background-color: #f7e373;
    color: black;
  }

  .plan-box {
    width: 80%;              /* Cambiar el ancho al 80% */
    aspect-ratio: 0.8;       /* Ajustar la relación de aspecto */
    background-color: #e2e2e2;
    border-radius: 1.5rem;
    padding: 1.5rem;         /* Reducir el padding */
}

  textarea {
    width: 100%;
    height: 100%;
    background: transparent;
    border: none;
    resize: none;
    color: black;
    font-family: inherit;
    font-size: 1rem;
  }

  textarea::placeholder {
    color: #666;
  }

  textarea:focus {
    outline: none;
  }

  .btn {
    padding: 1rem;
    background-color: #4CAF50;
    color: white;
    border-radius: 1rem;
    text-decoration: none;
    text-align: center;
    display: inline-block;
    margin-top: 1rem;
  }

  .btn:hover {
    background-color: #45a049;
  }

  @media (max-width: 768px) {
    .plans {
      flex-direction: column;
    }
  }
</style>
