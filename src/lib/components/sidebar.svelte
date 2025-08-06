
<script>
    import { page } from "$app/state";
    import { Instagram, Github, Linkedin } from "@lucide/svelte";
</script>

<aside>
    <nav class="socials-cont">
        <a target="_blank" href="https://www.instagram.com/tro.ylu"> <Instagram size={24}/> </a>
        <a target="_blank" href="https://github.com/troylu8"> <Github size={24}/> </a>
        <a target="_blank" href="https://www.linkedin.com/in/troy-lu"> <Linkedin size={24}/> </a>
    </nav>
    <p class="phone-number"> (909) 247 0187 </p>
    <p class="email"> troylu8@gmail.com </p>
    
    <nav class="site-links-cont" data-sveltekit-preload-data="hover">
        <a href="/" class={page.url.pathname == '/' ? "active-link" : ""}> Hey!! </a>
        <a href="/experiences" class={page.url.pathname == '/experiences' ? "active-link" : ""}> Experiences </a>
        <a href="/projects" class={page.url.pathname == '/projects' ? "active-link" : ""}> Projects </a>
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
    
    .socials-cont {
        display: flex;
        gap: 12px;
    }
    
    .phone-number, .email {
        font-family: JetBrainsMono, monospace;
        margin: 0;
        font-size: 0.85em;
    }
    
    .site-links-cont {
        display: flex;
        flex-direction: column;
        margin-top: 36px;
        gap: 12px;
    }
    .site-links-cont > a {
        align-self: flex-start;
        text-decoration: none;
        position: relative;
    }
    .site-links-cont > a::before {
        content: "#";
        padding-right: 6px;
    }
    .site-links-cont > a::after {
        content: "";
        position: absolute;
        bottom: 1.5px;
        left: 0;
        right: 0;
        height: 1.5px;
        background-color: currentColor;
    }
    
    .active-link {
        font-weight: bold;
        color: var(--accent2);
    }
</style>