<script lang="ts">
    import "$lib/global.css";
    import Sidebar from '$lib/components/sidebar.svelte';
	let { children } = $props();
</script>

<div id="content-outer">
    <header> <a href="/"> Troy Lu </a> </header>
    
    <div id="content-inner">
        <Sidebar />
        
        <main>
            {@render children?.()}
        </main>
    </div>
</div>

<style>
    header {
        width: 100%;
        text-align: center;
        font-size: 52px;
        margin-bottom: 16px;
    }
    header > a {
        font-family: Excalifont;
        text-decoration: none;
        color: var(--foreground);
    }
    
    #content-outer {
        max-width: 770px;
        margin: 0 auto;
        padding: 12px;
    }
    
    #content-inner {
        display: flex;
        gap: 32px;
    }
    
    @media (max-width: 800px) {
        #content-inner {
            flex-direction: column;
            gap: 12px;
        }
    }
</style>