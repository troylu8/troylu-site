
<script lang="ts">
    import { House } from "@lucide/svelte";
    import type { Snippet } from "svelte";

    type Props = {
        showBackArrow?: boolean
        children: Snippet<[]>
    }
    const { showBackArrow = true, children }: Props = $props();
</script>

<header>
    <h1> {@render children()} </h1>
    {#if showBackArrow}
        <a href="/" data-sveltekit-preload-data="tap">
            <House size={36} />
        </a>
    {/if}
</header>

<style>
    header {
        display: flex;
        justify-content: space-between;
        gap: 36px;
        align-items: center;
        padding: 12px;
        z-index: 10;
    }
    header > * {
        color: var(--accent2);
    }
    
    @media (max-width: 800px) {
        header {
            position: sticky;
            top: 0;
            background-color: var(--background);
        }
    }
</style>