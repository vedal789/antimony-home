<script>
    let is_navbar_closed = $state(true);
    function dropMenu() {
        is_navbar_closed = !is_navbar_closed;
    }
    import LINK from "../resources/urls.js";
</script>

<div class="navbar">
    <div class="content">
        <div class="navbar-row">
            <a href="/" class="logo">
                <img src="/logo_dark.svg" alt="Antimony" />
                <span>Antimony</span>
            </a>
            <button class="dropdown" onclick={dropMenu} aria-label="Toggle navigation">
                <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
                    <path d="M2 4.5H16M2 9H16M2 13.5H16" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" />
                </svg>
            </button>
        </div>
        <div class="links" class:closed={is_navbar_closed}>
            <a href={LINK.editor}>Create</a>
            <a href="/credits">Credits</a>
            <a href={LINK.discord} class="btn-link">Discord</a>
        </div>
    </div>
</div>

<style>
    .navbar {
        position: sticky;
        top: 0;
        z-index: 100;
        background: var(--bg-secondary);
        border-bottom: 1px solid var(--border-default);
    }

    .content {
        max-width: 880px;
        margin: 0 auto;
        padding: 0 var(--space-xl);
        display: flex;
        align-items: center;
        min-height: 52px;
    }

    .navbar-row {
        display: flex;
        align-items: center;
        width: 100%;
    }

    .logo {
        display: flex;
        align-items: center;
        gap: var(--space-sm);
        color: var(--text-primary);
        font-family: var(--font-ui);
        font-weight: 700;
        font-size: 14px;
        letter-spacing: -0.01em;
    }

    .logo:hover {
        color: var(--text-primary);
        opacity: 0.85;
    }

    .logo img {
        height: 22px;
        display: block;
    }

    .links {
        display: flex;
        align-items: center;
        gap: var(--space-xl);
        margin-left: auto;
    }

    .navbar a {
        color: var(--text-secondary);
        text-decoration: none;
        font-family: var(--font-ui);
        font-size: 13px;
        font-weight: 500;
        transition: color 0.12s ease;
    }

    .navbar a:hover {
        color: var(--text-primary);
    }

    .btn-link {
        color: var(--text-primary) !important;
        background: var(--bg-tertiary);
        border: 1px solid var(--border-default);
        border-radius: var(--radius-md);
        padding: 0.4rem 0.85rem;
    }

    .btn-link:hover {
        background: var(--bg-surface);
        border-color: var(--border-strong);
    }

    .dropdown {
        margin-left: auto;
        display: none;
        background: transparent;
        border: none;
        color: var(--text-secondary);
        padding: var(--space-sm);
        cursor: pointer;
    }

    @media (max-width: 600px) {
        .links {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            margin-left: 0;
            width: 100%;
            padding: var(--space-md) 0 var(--space-lg);
            gap: var(--space-md);
        }

        .content {
            flex-direction: column;
            align-items: stretch;
            padding: var(--space-sm) var(--space-xl);
        }

        .dropdown {
            display: flex;
        }

        .btn-link {
            align-self: flex-start;
        }

        .closed {
            display: none;
        }
    }
</style>