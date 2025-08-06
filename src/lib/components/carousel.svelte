<script lang="ts">
    import { CircleChevronLeft, CircleChevronRight } from '@lucide/svelte';
    
    type Props = {
        photos: {
            src: string
            alt?: string
        }[]
    }
    const { photos }: Props = $props();
    
    let i = $state(0);
    let currPhoto = $derived(photos[i]);
</script>


<div class="carousel">
    <CircleChevronLeft
        cursor="pointer" 
        size={48} 
        strokeWidth={1} 
        onclick={() => i = (i == 0)? photos.length - 1 : i - 1} 
    />
    <div class="fig">
        <img src={currPhoto.src} alt={currPhoto.alt}>
        <div class="caption"> 
            <span>{currPhoto.alt}</span>
            <span class="tracker"> {i + 1} / {photos.length} </span>
        </div>
    </div>
    <CircleChevronRight 
        cursor="pointer" 
        size={48} 
        strokeWidth={1} 
        onclick={() => i = (i == photos.length - 1) ? 0 : i + 1} 
    />
</div>

<style>
    .carousel {
        display: flex;
        align-items: center;
        justify-content: center;
        user-select: none;
        gap: 16px;
        margin-top: 24px;
        padding-bottom: 36px;
    }
    
    img {
        object-fit: cover;
        border: solid 2px var(--foreground);
        width: 100%;
        height: 100%;
    }
    
    .fig {
        position: relative;
        width: 70%;
        aspect-ratio: 16 / 9;
    }
    .caption {
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        display: flex;
        justify-content: space-between;
        font-size: small;
    }
    .tracker {
        font-family: JetBrainsMono, monospace;
        text-wrap: nowrap;
    }
    
    
</style>