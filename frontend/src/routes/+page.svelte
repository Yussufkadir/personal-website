<script lang="ts">
    let name = $state("Yusuf");
    let showDetails = $state(true);

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

<main>
    <h1>Portfolio and Personal Website.</h1>
    <p>I build AI applications and study AI.</p>

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
</style>