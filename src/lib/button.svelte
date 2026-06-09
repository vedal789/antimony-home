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
        style="text-decoration: none;"
    >
        <button
            class={(highlighted ? "button button-highlight" : "button") +
                (color ? ` ${color}` : "")}
            on:click={event}
        >
            {#if icon}
                <img src={`/${icon}`} alt={icon} style="margin-right:6px;" />
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
        on:click={event}
    >
        {#if icon}
            <img src={`/${icon}`} alt={icon} style="margin-right:6px;" />
        {/if}
        {@html label}
        <slot />
    </button>
{/if}

<style>
    .button {
        margin: 0.25rem;
        padding: 1rem 1rem;
        font-weight: 600;
        font-size: 1.1rem;
        border: 0px;
        border-radius: 4px;
        outline-width: 2px;
        outline-style: solid;
        outline-color: rgba(55, 0, 255, 0.35);
        color: white;
        background-color: #3700ff;
        cursor: pointer;
        display: flex;
        flex-direction: row;
        align-items: center;
    }
    .button:focus {
        outline-width: 4px;
    }
    .button-highlight {
        outline: 0px;
        background-color: white;
        color: #3700ff;
    }
    .button-toggled {
        background-color: transparent !important;
        outline-color: rgba(55, 0, 255, 0.35) !important;
        border: 1px solid rgba(55, 0, 255, 0.35);
        color: black;
        font-weight: normal;
    }
    :global(body.dark-mode) .button-toggled {
        outline-color: rgba(255, 255, 255, 0.1) !important;
        border: 1px solid rgba(255, 255, 255, 0.35);
        color: white;
    }

    .remix {
        background-color: #48ac72;
        outline-color: rgba(72, 172, 114, 0.35);
    }
    .gray {
        background-color: #797979;
        outline-color: rgba(112, 112, 112, 0.35);
    }
    .orange {
        background-color: #ffab00;
        outline-color: rgba(255, 171, 0, 0.35);
    }
    .red {
        background-color: #ff5151;
        outline-color: rgba(255, 81, 81, 0.35);
    }
    .purple {
        background-color: #ab51ff;
        outline-color: rgba(185, 81, 255, 0.35);
    }
</style>