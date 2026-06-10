<script>
    import Navbar from '$lib/navbar.svelte';
    import Button from '$lib/button.svelte';
</script>

<Navbar />

    <body>
        <div class="thingy">
            <h1>Antimony</h1>
            <p>Antimony is a a block-based video editing tool, built for newbies and power users.</p>

            <div class="center-wrapper-thingy">
                <Button 
                icon="startcreating.svg" // lucide my wife :3
                label="Start Creating!" 
                highlighted={true} 
                link="https://antimony-editor.github.io/editor/" 
        />
    </div>
</div>

<div class="footer">
    <p>Made with &lt;3 by the Antimony Team</p>
        <div class="footer2">
        
        <div class="footer-column">
            <h4>Website</h4>
            <a href="https://antimony-editor.github.io/editor/" style="color: white;"><p>Editor</p></a> 
            <a href="credits" style="color: white;"><p>Credits</p></a>
            <a href="https://github.com/antimony-editor" style="color: white;"><p>GitHub</p></a>
        </div>

        <div class="footer-column">
            <h4>Community</h4>
            <a href="https://github.com/vedal789/antimony-home/issues" style="color: white;"><p>Report an issue</p></a>
            <a href="https://discord.gg/CeJVMHXhCP" style="color: white;"><p>Discord</p></a>
        </div>

        <div class="footer-column">
            <h4>Funding</h4>
            <a href="support" style="color: white;"><p>Antimony</p></a>
        </div>
        
    </div>
</div>
</body>
