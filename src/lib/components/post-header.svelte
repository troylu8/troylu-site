<script lang="ts">
    type Props = {
        title: string,
        subtitle?: string,
        date?: string,
        links?: {icon?: string, href: string, label?: string}[]
    }
    const { title, subtitle, date, links }: Props = $props();
</script>

<header>
    <h2>{ title }</h2>
    <p class="subtitle">{ subtitle }</p>
</header>

<nav>
    {#if links}
        {#each links as link}
        <a href={link.href} target="_blank">
            <img src={"/img/icons/" + link.icon} width={16} alt={link.icon}>
            <span> {link.label} </span>
        </a>
        {/each}
    {/if}
        
    {#if date}
        <p class="date" style={links != undefined ? "margin-left: auto" : "" }>{ date }</p>
    {/if}
</nav>

<style>
    header {
        margin-top: 48px;
        color: var(--accent);
    }
    h2 {
        font-size: 1.7em;
        display: inline;
        margin-right: 12px;
    }
    .subtitle {
        font-size: 1.2em;
        display: inline;
        font-weight: bold;
    }
    
    nav {
        margin-top: 12px;
        margin-bottom: 24px;
        display: flex;
    }
    
    a {
        margin-right: 16px;
        display: inline-flex;
        align-items: center;
        gap: 8px;
        font-size: smaller;
    }
    
    .date {
        margin-block: 0;
    }
</style>