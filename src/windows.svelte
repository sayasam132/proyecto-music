<script>
    let currentTab = 'Música';
    const tabs = ['Música'];

    const genres = [
        { id: 1, name: 'Pop', icon: '💕' },
        { id: 2, name: 'Rock', icon: '🎸' },
        { id: 3, name: 'Electronica', icon: '💿' },
        { id: 4, name: 'Reggae', icon: '🎧' }
    ];

    const mixCards = [
        {
            title: 'album',
            image: '/mont.png',
            type: 'weekly'
        },
        {
            title: 'Mix diario',
            image: '/mont.png',
            type: 'daily'
        },
        {
            title: 'Música reciente',
            image: '/mont.png',
            type: 'recent'
        }
    ];

    const songCards = [
        {
            title: 'Mago de OZ: Adios Dulcinea',
            image: '/music.png',
        },
        {
            title: 'Zona Ganjah: Vibra positiva',
            image: '/mont.png',
        },
        {
            title: 'Tigres del Norte: Prision de amor',
            image: '/music.png',
        }
    ];
</script>

<div class="container">
    <header>        
        <div class="user-info">
            <h1>Buenos días</h1>
            <p>Samuel Mejia</p>
        </div>

        <nav class="tabs">
            {#each tabs as tab}
                <button
                    class="tab-button"
                    class:active={currentTab === tab}
                    on:click={() => currentTab = tab}
                >
                    {tab}
                </button>
            {/each}
        </nav>
    </header>

    <div class="genres-grid">
        {#each genres as genre}
            <button class="genre-card">
                <span class="genre-icon">{genre.icon}</span>
                <span class="genre-name">{genre.name}</span>
            </button>
        {/each}
    </div>

    <section>
        <h2>Para ti</h2>
        <div class="mix-grid">
            {#each mixCards as card}
                <div class="mix-card">
                    <img src={card.image} alt={card.title} />
                    <p>{card.title}</p>
                </div>
            {/each}
        </div>
    </section>

    <section>
        <h2>Lo más escuchado</h2>
        <div class="songs-grid">
            {#each songCards as card}
                <div class="song-card">
                    <img src={card.image} alt={card.title} />
                    <p>{card.title}</p>
                </div>
            {/each}
        </div>
    </section>
</div>

<style>
    .container {
        background-color: #1a1e21;
        color: white;
        min-height: 100vh;
        padding: 20px;
    }

    header {
        margin-bottom: 24px;
    }

    .user-info h1 {
        font-size: 2rem;
        margin: 0;
    }

    .user-info p {
        color: #a0a0a0;
        margin: 4px 0 16px 0;
    }

    .tabs {
        display: flex;
        gap: 12px;
        margin-bottom: 24px;
    }

    .tab-button {
        background-color: #2a2f33;
        border: none;
        color: white;
        padding: 8px 16px;
        border-radius: 20px;
        cursor: pointer;
    }

    .tab-button.active {
        background-color: #3a3f43;
    }

    .genres-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 16px;
        margin-bottom: 32px;
    }

    .genre-card {
        display: flex;
        align-items: center;
        background-color: #2a2f33;
        border: none;
        color: white;
        padding: 16px;
        border-radius: 8px;
        cursor: pointer;
        text-align: left;
    }

    .genre-icon {
        font-size: 1.5rem;
        margin-right: 12px;
    }

    section h2 {
        font-size: 1.5rem;
        margin-bottom: 16px;
    }

    .mix-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 16px;
        margin-bottom: 32px;
    }

    .songs-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 16px;
    }

    .mix-card, .song-card {
        position: relative;
        border-radius: 8px;
        overflow: hidden;
    }

    .mix-card img, .song-card img {
        width: 100%;
        height: 200px;
        object-fit: cover;
    }

    .mix-card p, .song-card p {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        padding: 16px;
        margin: 0;
        background: linear-gradient(transparent, rgba(0,0,0,0.8));
        color: white;
    }

    @media (max-width: 768px) {
        .genres-grid {
            grid-template-columns: repeat(2, 1fr);
        }

        .mix-grid, .songs-grid {
            grid-template-columns: 1fr;
        }
    }
</style>
