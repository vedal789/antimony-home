<script>
    import Navbar from "$lib/navbar.svelte";
    import Button from "$lib/button.svelte";
</script>

<Navbar />

<div class="support-container">
    <small
        >This page is a work in progress. It may be incomplete or inaccurate.</small
    >
    <h1>Support Antimony</h1>
    <p>
        Antimony costs money to maintain and improve. Your support helps us keep
        the project alive and growing!
    </p>
</div>

<style>
    .support-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
</style>
