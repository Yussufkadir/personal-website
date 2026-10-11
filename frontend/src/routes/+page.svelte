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
    }
</style>