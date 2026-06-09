<script>
    let is_navbar_closed = $state(true);
    function dropMenu() {
        is_navbar_closed = !is_navbar_closed;
    }
</script>

<div class="navbar">
    <div class="content">
        <div style="display: flex; width: 100%">
            <a href="/" class="logo">
                <img src="/logo_dark.svg" alt="Antimony" />
            </a>
            <button class="dropdown" onclick={dropMenu}>x</button>
        </div>
        <div class="links" class:closed={is_navbar_closed}>
            <a href="https://antimony-editor.github.io/editor/" style="text-decoration: none"><p>Create</p></a>
            <a href="https://discord.gg/CeJVMHXhCP" style="text-decoration: none"><p>Discord</p></a>
        </div>
    </div>
</div>

<style>
    .navbar{
			  position: sticky;
        top: 0;
        background-color: rgb(24, 22, 100);
        padding: 1rem;
        text-align: center;
    }
    .content{
        max-width: 800px;
        margin-left: auto;
        margin-right: auto;
        display: flex;
				align-items: center;
    }
    .links {
        display: flex;
        gap: 1rem;
        margin-left: auto;
    }
    .navbar a {
        color: white;
        text-decoration: none;
        font-size: 1.0rem;
    }

    .navbar a:hover {
        color: rgb(200, 200, 255);
        font-size: 1.04rem;
    }

    .logo img {
        height: 40px;
        display: block;
    }
    
    .logo img:hover {
        height: 41px;
        display: block;
        opacity: 0.8;
    }

    .dropdown {
        margin-left: auto;
        display: none;
    }
	
    @media (max-width:530px){
        .links {
            display: flex;
            position: sticky;
            flex-direction: column;
            margin-left: auto;
            margin-right: auto;
            width: 100%;
        }
        .navbar {
            flex-direction: column;
        }
        .dropdown {
            display: block;
        }
				.content {
						display: block;
				}
        .closed {
            display: none;
        }
    }
</style>