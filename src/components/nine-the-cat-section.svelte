<script lang="ts">
    
    const PICTURE_COUNT = 9;
    
    let purrText: HTMLParagraphElement | undefined;
    
    function onPet() {
        if (!purrText) return;
        
        purrText.style.animation = "none";
        void purrText.offsetHeight;
        purrText.style.animation = "";
    }
    
    function getFormattedDate() {
        const today = new Date();
        const year = today.getFullYear();
        const month = 1 + today.getMonth()
        const day = today.getDate();
        return month + '/' + day + '/' + year;
    }
    
    function getTodaysPic() {
        const DAYS_SINCE_EPOCH = Math.floor(Date.now() / 8.64e7);
        return `/img/cat-pics/${DAYS_SINCE_EPOCH % PICTURE_COUNT}.jpg`; // pics are named 0.jpg, 1.jpg, 2.jpg, ...
    }
</script>

<h1> Nine the cat </h1>
<p>This is my family cat, Nine. Her hobbies are sleeping, eating, sleeping, and sleeping.</p>
<p><span id="date"> [ { getFormattedDate() } ] </span> Today's cat picture: </p>
<section>
    <img src={getTodaysPic()} height={300} alt="Nine the cat" />
    <button class="main-btn" onclick={onPet}> Pet her </button>
    <p id="purr-text" style="animation: none;" bind:this={purrText}> * she gives you a soft purr </p>
</section>

<style>
    section {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 16px;
    }
    #purr-text {
        transition: 200ms;
        user-select: none;
        opacity: 0;
        animation: purr-anim 1.5s linear forwards;
    }
    @keyframes purr-anim {
        0% {
            opacity: 0;
        }
        10% {
            opacity: 1;
        }
        90% {
            opacity: 1;
        }
        100% {
            opacity: 0;
        }
    }
    
    #date {
        font-family: monospace;
        font-size: large;
        margin-right: 12px;
    }
</style>