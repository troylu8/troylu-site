<script lang="ts">
    import { Github, Globe } from "@lucide/svelte";
    
    type Props = {
        title: string,
        date: string,
        links?: {icon?: string, href: string, label?: string}[]
    }
    const { title, date, links }: Props = $props();
</script>


<h1>{ title }</h1>
<p>{ date }</p>

{#if links}
    <nav>
        {#each links as link}
            <a href={link.href} target="_blank">
                <img src={"/img/icons/" + link.icon} width={16} alt={link.icon}>
                <span> {link.label} </span>
            </a>
        {/each}
    </nav>
{/if}

<style>
    a {
        font-family: monospace;
        margin-right: 16px;
        display: inline-flex;
        align-items: center;
        gap: 8px;
    }
    
    img {
        border-radius: 4px;
    }
</style>