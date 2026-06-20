<script>
    import Navbar from '$lib/navbar.svelte';
    import Button from '$lib/button.svelte';
</script>

<Navbar />

<main class="content-wrapper credits-container">
    <h1>Credits</h1>
    <p class="lede">Antimony is built and maintained by volunteers. This page recognizes the people who keep the project running.</p>

    <section class="block">
        <h2>Active Contributors</h2>
        <ul class="contributor-list">
            <li>
                <img src="https://github.com/Gen1xLol.png" alt="Gen1xLol's avatar">
                <a href="https://github.com/Gen1xLol">Gen1xLol</a>
            </li>
            <li>
                <img src="https://github.com/thedotun.png" alt="thedotun's avatar">
                <a href="https://github.com/thedotun">thedotun</a>
            </li>
            <li>
                <img src="https://github.com/UnbraveChimp.png" alt="UnbraveChimp's avatar">
                <a href="https://github.com/UnbraveChimp">UnbraveChimp</a>
            </li>
            <li>
                <img src="https://github.com/LordCat0.png" alt="LordCat0's avatar">
                <a href="https://github.com/LordCat0">LordCat0</a>
            </li>
            <li>
                <img src="https://github.com/ddededodediamante.png" alt="ddededodediamante's avatar">
                <a href="https://github.com/ddededodediamante">ddededodediamante</a>
            </li>
            <li>
                <img src="https://github.com/vedal789.png" alt="vedal789's avatar">
                <a href="https://github.com/vedal789">vedal789</a>
            </li>
            <li>
                <img src="https://github.com/PuzzlingGGG.png" alt="PuzzlingGGG's avatar">
                <a href="https://github.com/PuzzlingGGG">PuzzlingGGG</a>
            </li>
        </ul>
    </section>

    <section class="block">
        <h2>Server Host</h2>
        <div class="panel host-panel">
            <div class="panel-body host-panel-body">
                <img class="host-pfp" src="https://github.com/lordcat0.png" alt="lordcat0's avatar">
                <p class="host-text">
                    Antimony's backend API is currently developed and hosted by
                    <a href="https://github.com/lordcat0">lordcat</a>.
                </p>
            </div>
        </div>
    </section>
</main>

<style>
    .credits-container {
        max-width: 720px;
    }

    .lede {
        font-size: 1rem;
        max-width: 56ch;
    }

    .block {
        margin-top: var(--space-2xl);
    }

    .contributor-list {
        list-style: none;
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
        gap: var(--space-sm);
        margin: 0;
        padding: 0;
    }

    .contributor-list li {
        display: flex;
        align-items: center;
        gap: var(--space-md);
        background: var(--bg-primary);
        border: 1px solid var(--border-default);
        border-radius: var(--radius-lg);
        padding: var(--space-sm) var(--space-md);
        transition: border-color 0.15s ease, background 0.15s ease;
    }

    .contributor-list li:hover {
        border-color: var(--border-strong);
        background: var(--bg-secondary);
    }

    .contributor-list img {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        object-fit: cover;
        flex-shrink: 0;
    }

    .contributor-list a {
        color: var(--text-primary);
        font-weight: 500;
        font-size: 14px;
    }

    .contributor-list a:hover {
        color: var(--accent-hover);
    }

    .host-panel-body {
        display: flex;
        align-items: center;
        gap: var(--space-lg);
    }

    .host-pfp {
        width: 64px;
        height: 64px;
        border-radius: 50%;
        object-fit: cover;
        flex-shrink: 0;
    }

    .host-text {
        margin: 0;
    }

    @media (max-width: 480px) {
        .host-panel-body {
            flex-direction: column;
            text-align: center;
        }
    }
</style>