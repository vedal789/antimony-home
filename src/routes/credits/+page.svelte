<script>
    import Navbar from '$lib/navbar.svelte';
    import Button from '$lib/button.svelte';
</script>

<Navbar />

<main class="credits-container">
        <h1>Credits</h1>
        <p>Antimony is made possible by the work of many volunteers. We want to thank everyone who has contributed to the project.</p>

    <section class="contributors-section">
        <h2>Active Contributors</h2>
        <ul class="contributors-list">
            <li>
                <img src="https://github.com/Gen1xLol.png" alt="Gen1xLol's avatar">
                <span><a href="https://github.com/Gen1xLol" style="color: white;"><p>Gen1xLol</p></a></span>
            </li>
            <li>
                <img src="https://github.com/thedotun.png" alt="thedotun's avatar">
                <span><a href="https://github.com/thedotun" style="color: white;"><p>thedotun</p></a></span>
            </li>
            <li>
                <img src="https://github.com/UnbraveChimp.png" alt="UnbraveChimp's avatar">
                <span><a href="https://github.com/UnbraveChimp" style="color: white;"><p>UnbraveChimp</p></a></span>
            </li>
            <li>
                <img src="https://github.com/LordCat0.png" alt="LordCat0's avatar">
                <span><a href="https://github.com/LordCat0" style="color: white;"><p>LordCat0</p></a></span>
            </li>
            <li>
                <img src="https://github.com/ddededodediamante.png" alt="ddededodediamante's avatar">
                <span><a href="https://github.com/ddededodediamante" style="color: white;"><p>ddededodediamante</p></a></span>
            </li>
            <li>
                <img src="https://github.com/vedal789.png" alt="vedal789's avatar">
                <span><a href="https://github.com/vedal789" style="color: white;"><p>vedal789</p></a></span>
            </li>
            <li>
                <img src="https://github.com/PuzzlingGGG.png" alt="PuzzlingGGG's avatar">
                <span><a href="https://github.com/PuzzlingGGG" style="color: white;"><p>PuzzlingGGG</p></a></span>
            </li>
        </ul>
    </section>
</main>

<style>

    .credits-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }

    .contributors-section {
        margin-top: 40px;
        width: 100%;
    }

    .contributors-list {
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        align-items: center;
    }

    .contributors-list li {
        display: flex;
        align-items: center;
        border: 3px solid rgba(59, 56, 202, 0.1);
        padding: 10px 20px;
        border-radius: 12px;
        width: 100%;
        max-width: 350px;
    }

    .contributors-list li:hover {
        background: rgba(46, 49, 247, 0.1);
    }

    .contributors-list img{
        width: 50px;
        height: 50px;
        border-radius: 50%;
        margin-right: 15px;
        object-fit: cover;
    }

    .contributors-list span {
        font-size: 1.1rem;
        font-weight: 500;
    }
</style>