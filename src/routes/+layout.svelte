<script lang="ts">
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
        font-size: 48px;
        margin-left: 15cqw;
        margin-bottom: 16px;
    }
    
    #content-outer {
        max-width: 800px;
        margin: 30px auto;
        padding: 12px;
    }
    
    #content-inner {
        display: flex;
        gap: 32px;
    }
</style>