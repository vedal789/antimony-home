<script>
  import { page } from '$app/stores';

</script>

<h1>{$page.status}</h1>

<p>{$page.error?.message}</p>

{#if $page.status === 404}
  <p>Aaaa! The page you're looking for doesn't exist.</p>
  <a href="/">Go back home</a>
{/if}