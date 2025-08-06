<script>
    import NineTheCatSection from "$lib/components/nine-the-cat-section.svelte";
    import PageHeader from "$lib/components/page-header.svelte";
</script>

<PageHeader showBackArrow={false}> Hey!! </PageHeader>
<p>
    I'm a computer science student who isn't afraid to learn new things.
</p>
<p>
    Full-stack web development is what excites me the most. <br>
    Check out the cool things I've built over at 
    <a class="inline-link" href="/projects" data-sveltekit-preload-data="hover">#projects</a> 
    !
</p>
<p>
    Lately, I've been really into jpop and vocaloid music. <br>
    It's full of energy in a unique way.
</p>
<nav data-sveltekit-preload-data="hover">
    <a class="main-btn" href="/experiences">Experiences </a>
    <a class="main-btn" href="/projects"> Projects </a>
</nav>


<NineTheCatSection />

<style>
    nav {
        margin-block: 36px;
        display: flex;
        gap: 18px;
        justify-content: center;
    }
    nav > a {
        font-size: large;
    }
    
    @media (max-width: 500px) {
        nav {
            flex-direction: column;
            align-items: center;
        }
    }
    
    .inline-link {
        font-family: inherit;
    }
</style>