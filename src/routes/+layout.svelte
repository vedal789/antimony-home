<script>
    import favicon from "/logo.svg";
    import "$lib/assets/style.css";

    let { children } = $props();
</script>

<svelte:head>
    <title>Antimony - Home</title>
    <link rel="icon" href={favicon} />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link
        rel="preconnect"
        href="https://fonts.gstatic.com"
        crossorigin="anonymous"
    />
    <link
        href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap"
        rel="stylesheet"
    />

    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link
        rel="preconnect"
        href="https://fonts.gstatic.com"
        crossorigin="anonymous"
    />
    <link
        href="https://fonts.googleapis.com/css2?family=Black+Ops+One&display=swap"
        rel="stylesheet"
    />
</svelte:head>

<div class="page">
    {@render children()}
    <div class="footer">
        <br />
        <!-- stupid way to do it but fuck it -->
        <p style="text-align: center;">Made with &lt;3 by the Antimony Team</p>
        <br />
        <div class="footer2">
            <div class="footer-column">
                <h4>Website</h4>
                <a href="https://editor.antimony.cc" style="color: white;"
                    ><p>Editor</p></a
                >
                <a href="desktop" style="color: white;"><p>Desktop App</p></a>
                <a href="credits" style="color: white;"><p>Credits</p></a>
                <a
                    href="https://github.com/antimony-editor"
                    style="color: white;"><p>GitHub</p></a
                >
            </div>

            <div class="footer-column">
                <h4>Community</h4>
                <a
                    href="https://github.com/antimony-editor/antimony-home/issues"
                    style="color: white;"><p>Report an issue</p></a
                >
                <a
                    href="https://www.youtube.com/channel/UCuC_CpmCqhKV6g0I33s6PJQ"
                    style="color: white;"><p>YouTube</p></a
                >
                <a href="https://discord.gg/CeJVMHXhCP" style="color: white;"
                    ><p>Discord</p></a
                >
            </div>
        </div>
    </div>
</div>
