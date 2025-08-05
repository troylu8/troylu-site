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


<div>
    <CircleChevronLeft 
        cursor="pointer" 
        size={48} 
        strokeWidth={1} 
        onclick={() => i = (i == 0)? photos.length - 1 : i - 1} 
    />
    <figure>
        <img src={currPhoto.src} alt={currPhoto.alt} height={250} width={445}>
        <figcaption> 
            <span>{currPhoto.alt}</span>
            <span class="tracker"> {i + 1} / {photos.length} </span>
        </figcaption>
    </figure>
    <CircleChevronRight 
        cursor="pointer" 
        size={48} 
        strokeWidth={1} 
        onclick={() => i = (i == photos.length - 1) ? 0 : i + 1} 
    />
</div>

<style>
    div {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 16px;
        user-select: none;
    }
    
    img {
        object-fit: cover;
    }
    
    figcaption {
        display: flex;
        justify-content: space-between;
        font-size: small;
    }
    .tracker {
        font-family: monospace;
    }
</style>