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
<small>small text test</small>
</body>