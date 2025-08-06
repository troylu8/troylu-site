<script lang="ts">
    import "$lib/global.css";
    import Sidebar from '$lib/components/sidebar.svelte';
	let { children } = $props();
</script>

<svelte:head>
    <title>Troy Lu</title>
</svelte:head>

<div id="content-outer">
    <header> Troy Lu </header>
    
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
        font-family: Excalifont;
        /* margin-left: 15cqw; */
        margin-bottom: 16px;
    }
    
    #content-outer {
        width: 800px;
        margin: 30px auto;
        padding: 12px;
    }
    
    #content-inner {
        display: flex;
        gap: 32px;
    }
</style>