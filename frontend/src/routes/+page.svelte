<script lang="ts">
    let name = $state("Yusuf");
    let showDetails = $state(true);

    const navItems = [
        { href: "/", label: "Home" },
        { href: "Projects", label: "Projects" },
        { href: "About", label: "About" }
    ];

    const skills = ["Python", "Deep Learning", "LLM"]

    function toggleDetails() {
        showDetails = !showDetails
    } 

</script>

<svelte:head>
    <title>{name} | Portfolio</title>
    <meta
        name="description"
        content="Personal portfolio and software projects."
    />
</svelte:head>

<header>
    <nav aria-label="Main navigation">
        <a class="logo" href="/">YS</a>

        <div class="nav-links">
            {#each navItems as item}
                <a href={item.href}>{item.label}</a>
            {/each}
        </div>
    </nav>
</header>

<main>
    <section class="hero"> 
        <p class="eyebrow"> AI developer </p>
        <h1>Yussufkadir Syurmen</h1>
        <p>Building AI products with Metal, Python, FastAPI, Svelte</p>
    </section>


    <section class="what-doing">
    <h2>What I develop</h2>
    <div class="card-grid">
        <article class="card">
            <h3>AI development</h3>
            <p>Efficient and need based AI tool development</p>
        </article>

        <article class="card">
            <h3>Full-stack development</h3>
            <p>Building websites that are easy to use and simple</p>
        </article>
    </div>
    </section>

    <button onclick={toggleDetails}>
        {showDetails ? "Hide skills": "Show skills"}
    </button>

    {#if showDetails}
        <h2>skills</h2>

        <ul>
            {#each skills as skill}
                <li>{skill}</li>
            {/each}
        </ul>
    {/if}
</main>

<style>
    :global(body) {
        font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        margin: 0;
        min-height: 100vh;
        color: rgba(191, 201, 173, 0.697);
        background-color: #050505;
        background-size: 24px 24px;
    }
    header {
        width: 100%;
        padding: 1.25rem 0;
    }

    nav {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
    }

    .nav-links {
        display: flex;
        gap: 1.5rem;
    }

    a {
        color: #d4d4d8;
        text-decoration: none;
        font-weight: 500;
    }
    a:hover {
        color: #ffffff
    }

    main {
        max-width: 900px;
        margin: 0 auto;
        padding: 4rem 1.5rem;
    } 

    h1 {
        font-size: 3rem;
    }

    button {
        padding: 0.75rem 1rem;
        cursor: pointer;
    }

    .eyebrow {
        color: rgba(191, 201, 173, 0.697);
        font-size: 0.85rem;
        font-weight: 700;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        text-align: center;
    }

    .what-doing {
        padding: 5rem 0;
    }

    .card-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1rem;
        margin-top: 2rem;
    }

    .card {
        padding: 1.5rem;
        border: 1px solid #27272a;
        border-radius: 1rem;
        background: rgb(24 24 27 / 80%);
    }

    .card h3 {
        margin-top: 0;
        color: #fafafa;
    }

    .card p {
        margin-bottom: 0;
        color: #a1a1aa;
        line-height: 1.6;
    }

    @media (max-width: 800px) {
        .card-grid {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media (max-width: 500px) {
        .card-grid {
            grid-template-columns: 1fr;
        }
    }


</style>