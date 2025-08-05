
<script>
    import { Instagram, Github, Linkedin } from "@lucide/svelte";
</script>

<aside>
    <nav>
        <a target="_blank" href="https://www.instagram.com/tro.ylu" > <Instagram size={24}/> </a>
        <a target="_blank" href="https://github.com/troylu8"> <Github size={24}/> </a>
        <a target="_blank" href="https://www.linkedin.com/in/troy-lu"> <Linkedin size={24}/> </a>
    </nav>
    <p class="phone-number"> (909) 247 0187 </p>
    <p class="email"> troylu8@gmail.com </p>
    
    <nav class="site-links" data-sveltekit-preload-data="hover">
        <a href="/"> Hey!! </a>
        <a href="/experiences"> Experiences </a>
        <a href="/projects"> Projects </a>
    </nav>
</aside>


<style>
    aside {
        position: sticky;
        top: 50px;
        height: fit-content;
        
        display: flex;
        flex-direction: column;
        gap: 12px
    }
    
    .phone-number, .email {
        font-family: monospace;
    }
    
    .site-links {
        display: flex;
        flex-direction: column;
    }
</style>