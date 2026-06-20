<script>
  import { page } from '$app/stores';
  import Navbar from '$lib/navbar.svelte';
</script>

<Navbar />

<main class="content-wrapper error-container">
  <span class="eyebrow">Error {$page.status}</span>
  <h1>{$page.status === 404 ? "Page not found" : "Whoops! Something went wrong..."}</h1>

  {#if $page.error?.message && $page.status != 404}
    <p class="error-message">{$page.error.message}</p>
  {/if}

  {#if $page.status === 404}
    <p>The page you're looking for doesn't exist, or may have moved.</p>
  {/if}

  <a href="/" class="btn primary">Back to home</a>
</main>

<style>
  .error-container {
    max-width: 560px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .error-message {
    font-family: var(--font-ui);
    font-size: 13px;
    color: var(--text-muted);
    background: var(--bg-primary);
    border: 1px solid var(--border-default);
    border-radius: var(--radius-md);
    padding: var(--space-sm) var(--space-md);
    display: inline-block;
  }

  .error-container .btn {
    margin-top: var(--space-lg);
    text-decoration: none;
  }
</style>