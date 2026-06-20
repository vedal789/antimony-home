<script>
    // thanks penguinmod for the button code <3
    // https://github.com/PenguinMod/PenguinMod-Home/blob/main/src/lib/Button/Button.svelte

    import { createEventDispatcher } from "svelte";

    const {
        highlighted = false,
        link = false,
        toggled = false,
        label = "",
        noredirect = false,
        icon = false,
        color = false,
    } = $props();

    const dispatch = createEventDispatcher();

    function event() {
        dispatch("click");
    }
</script>

{#if link}
    <a
        href={link}
        target={noredirect ? "_blank" : "_self"}
        class="button-link"
    >
        <button
            class={(highlighted ? "button button-highlight" : "button") +
                (color ? ` ${color}` : "")}
            onclick={event}
        >
            {#if icon}
                <img src={`/${icon}`} alt={icon} class="button-icon" />
            {/if}
            {@html label}
            <slot />
        </button>
    </a>
{/if}
{#if !link}
    <button
        class={(highlighted ? "button button-highlight" : "button") +
            (color ? ` ${color}` : "") +
            (toggled ? " button-toggled" : "")}
        onclick={event}
    >
        {#if icon}
            <img src={`/${icon}`} alt={icon} class="button-icon" />
        {/if}
        {@html label}
        <slot />
    </button>
{/if}

<style>
    .button-link {
        text-decoration: none;
        display: inline-block;
    }

    .button {
        margin: 0.25rem;
        padding: 0.65rem 1.1rem;
        font-family: var(--font-ui);
        font-weight: 600;
        font-size: 13px;
        border: 1px solid var(--border-default);
        border-radius: var(--radius-md);
        color: var(--text-primary);
        background-color: var(--bg-tertiary);
        cursor: pointer;
        display: inline-flex;
        flex-direction: row;
        align-items: center;
        transition: all 0.15s ease;
    }

    .button:hover {
        background-color: var(--bg-surface);
        border-color: var(--border-strong);
    }

    .button:focus-visible {
        outline: 2px solid var(--accent);
        outline-offset: 2px;
    }

    .button-icon {
        width: 16px;
        height: 16px;
        margin-right: 0.5rem;
    }

    .button-highlight {
        background-color: var(--accent);
        border-color: var(--accent);
        color: #fff;
    }

    .button-highlight:hover {
        background-color: var(--accent-hover);
        border-color: var(--accent-hover);
    }

    .button-toggled {
        background-color: var(--accent-dim) !important;
        border-color: var(--accent) !important;
        color: var(--accent);
        font-weight: 600;
    }

    .remix {
        background-color: rgba(34, 197, 94, 0.12);
        border-color: rgba(34, 197, 94, 0.4);
        color: var(--success);
    }
    .remix:hover {
        background-color: rgba(34, 197, 94, 0.18);
    }

    .gray {
        background-color: var(--bg-secondary);
        border-color: var(--border-default);
        color: var(--text-secondary);
    }

    .orange {
        background-color: rgba(232, 148, 10, 0.12);
        border-color: rgba(232, 148, 10, 0.4);
        color: var(--warning);
    }
    .orange:hover {
        background-color: rgba(232, 148, 10, 0.18);
    }

    .red {
        background-color: rgba(224, 62, 62, 0.12);
        border-color: rgba(224, 62, 62, 0.4);
        color: var(--danger);
    }
    .red:hover {
        background-color: rgba(224, 62, 62, 0.18);
    }

    .purple {
        background-color: rgba(168, 85, 247, 0.12);
        border-color: rgba(168, 85, 247, 0.4);
        color: #c08bff;
    }
    .purple:hover {
        background-color: rgba(168, 85, 247, 0.18);
    }
</style>