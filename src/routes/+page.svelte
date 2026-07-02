<script>
    import Navbar from "$lib/navbar.svelte";
    import Button from "$lib/button.svelte";
    import LINK from "../resources/urls.js";

    const WORDMARK_COLORS = ["#fdc700", "#ff6467", "#51a2ff"];
    const wordmark = "ANTIMONY".split("").map((char, i) => ({
        char,
        color: WORDMARK_COLORS[i % WORDMARK_COLORS.length],
        inDelay: i * 0.05,
        floatDelay: 0.6 + i * 0.15,
    }));
</script>

<Navbar />

<main>
    <section class="hero">
        <div class="hero-inner">
            <p class="hero-eyebrow">Welcome to</p>
            <h1 class="hero-title">
                {#each wordmark as letter}
                    <span
                        style="--letter-color: {letter.color}; --in-delay: {letter.inDelay}s; --float-delay: {letter.floatDelay}s;"
                        >{letter.char}</span
                    >
                {/each}
            </h1>
            <p class="hero-subtitle">Video, block by block.</p>
            <p class="hero-desc">
                Antimony is a block-based video editor. You build your edit by
                snapping blocks together, the same idea as block-based
                programming, just applied to video.
            </p>
            <div class="hero-actions">
                <Button
                    highlighted={true}
                    link={LINK?.editor ?? "/editor"}
                    label="Open the editor"
                />
                <Button link="/credits" label="See who built it" />
            </div>
        </div>
    </section>

    <section class="content-wrapper why-section">
        <span class="eyebrow">Why Antimony</span>
        <h2>Editing video shouldn't require a manual</h2>
        <p class="section-lede">
            A lot of video editors just expect you to already know where
            everything is: each menu, hotkey, and part of the timeline. Antimony
            skips most of that.
        </p>

        <div class="feature-grid">
            <div class="panel feature-card">
                <div class="panel-body">
                    <h3>Built for accessibility</h3>
                    <p>
                        Every action in your edit is a block you can actually
                        see. Nothing is hidden from you inside three different
                        menus.
                    </p>
                </div>
            </div>

            <div class="panel feature-card">
                <div class="panel-body">
                    <h3>Absolutely nothing to memorize</h3>
                    <p>
                        Blocks only click where they're meant to. There's no
                        need to remember syntax or the right order to do things.
                        If it fits, it'll work.
                    </p>
                </div>
            </div>

            <div class="panel feature-card">
                <div class="panel-body">
                    <h3>An edit you can actually read</h3>
                    <p>
                        Since the whole sequence is laid out as blocks, you can
                        look at an edit and tell what it does. That helps
                        whether it's your own project or one that you downloaded
                        off somewhere.
                    </p>
                </div>
            </div>

            <div class="panel feature-card">
                <div class="panel-body">
                    <h3>Built 100% in the open</h3>
                    <p>
                        Antimony is built by volunteers on GitHub instead of
                        remaining solely behind closed doors. That keeps the
                        project honest about what it can and can't do yet, and
                        allows people to freely contribute to it!
                    </p>
                </div>
            </div>
        </div>
    </section>

    <section class="content-wrapper cta-section">
        <div class="panel cta-panel">
            <div class="panel-body cta-body">
                <h2>Try making something cool!</h2>
                <p>
                    Antimony is <b>still in development</b> and may be prone to bugs.
                </p>
                <Button
                    highlighted={true}
                    link={LINK.editor}
                    label="Open the editor"
                />
            </div>
        </div>
    </section>
</main>

<style>
    .hero {
        border-bottom: 1px solid var(--border-default);
        background:
            radial-gradient(
                ellipse 60% 50% at 50% 0%,
                var(--accent-dim),
                transparent
            ),
            var(--bg-secondary);
        padding: var(--space-3xl) var(--space-xl);
    }

    .hero-inner {
        max-width: 720px;
        margin: 0 auto;
        text-align: center;
    }

    .hero-eyebrow {
        color: var(--text-secondary);
        font-size: 14px;
        font-weight: 500;
        text-transform: uppercase;
        letter-spacing: 0.1em;
        margin-bottom: var(--space-xs);
    }

    .hero-title {
        font-size: 72px;
        font-weight: 900;
        letter-spacing: -0.02em;
        line-height: 1;
        margin: 0 0 var(--space-sm);
        font-family: "Black Ops One", system-ui;
    }

    .hero-title :global(span) {
        display: inline-block;
        color: var(--letter-color);
        text-shadow:
            color-mix(in srgb, var(--letter-color) 20%, transparent) 0 0 10px,
            color-mix(in srgb, var(--letter-color) 13%, transparent) 0 0 20px;
        opacity: 0;
        transform: translateY(20px) scale(0.8);
        will-change: transform;
        animation:
            char-in 0.6s var(--in-delay) cubic-bezier(0.34, 1.56, 0.64, 1)
                forwards,
            char-float 3s ease-in-out infinite calc(-1 * var(--float-delay));
    }

    @keyframes char-in {
        to {
            opacity: 1;
            transform: translateY(0) scale(1);
        }
    }

    @keyframes char-float {
        0%,
        100% {
            transform: translateY(0);
        }
        50% {
            transform: translateY(-5px);
        }
    }

    .hero-subtitle {
        color: var(--text-primary);
        font-size: 20px;
        font-weight: 600;
        margin-bottom: var(--space-lg);
    }

    .hero-desc {
        max-width: 56ch;
        margin: 0 auto var(--space-xl);
        font-size: 15px;
    }

    .hero-actions {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: var(--space-sm);
    }

    .why-section {
        padding-top: var(--space-3xl);
        padding-bottom: var(--space-2xl);
    }

    .section-lede {
        max-width: 60ch;
        font-size: 1rem;
        margin-bottom: var(--space-2xl);
    }

    .feature-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: var(--space-lg);
    }

    .feature-card .panel-body {
        display: flex;
        flex-direction: column;
        gap: var(--space-sm);
    }

    .feature-block {
        display: block;
        width: 22px;
        height: 22px;
        border-radius: var(--radius-sm);
        flex-shrink: 0;
    }

    .feature-block-a {
        background: linear-gradient(
            135deg,
            var(--accent) 0%,
            var(--accent-hover) 100%
        );
        box-shadow: 0 0 10px var(--accent-glow);
    }

    .feature-block-b {
        background: linear-gradient(135deg, var(--success) 0%, #4ade80 100%);
        box-shadow: 0 0 10px rgba(34, 197, 94, 0.25);
    }

    .feature-block-c {
        background: linear-gradient(135deg, var(--warning) 0%, #fbbf24 100%);
        box-shadow: 0 0 10px rgba(232, 148, 10, 0.25);
    }

    .feature-block-d {
        background: linear-gradient(135deg, #ab51ff 0%, #c08bff 100%);
        box-shadow: 0 0 10px rgba(171, 81, 255, 0.25);
    }

    .feature-card h3 {
        margin: 0;
    }

    .feature-card p {
        margin: 0;
        font-size: 14px;
    }

    .cta-section {
        padding-top: 0;
        padding-bottom: var(--space-3xl);
    }

    .cta-panel {
        background: var(--bg-secondary);
    }

    .cta-body {
        text-align: center;
        padding: var(--space-2xl);
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: var(--space-xs);
    }

    .cta-body h2 {
        margin-bottom: 0;
    }

    .cta-body p {
        margin-bottom: var(--space-lg);
    }

    @media (max-width: 640px) {
        .hero-title {
            font-size: 48px;
        }

        .feature-grid {
            grid-template-columns: 1fr;
        }
    }
</style>
