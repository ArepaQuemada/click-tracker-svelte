
<script lang="ts">
	import { createEventDispatcher } from "svelte";
	import ButtonSection from "../components/ButtonSection.svelte";
	import CssReset from "../css-reset/CssReset.svelte";
    
    const dispatch = createEventDispatcher()

    function handleClickScreen(e: MouseEvent){
        dispatch('add-circle', {
            x: e.clientX,
            y: e.clientY
        })
    }

    function handleClickButton(e: MouseEvent) {
        const target = e.currentTarget as EventTarget & HTMLButtonElement;     
        dispatch('action-button', {
            action: target.name
        })
    }

</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<main on:click={handleClickScreen}>
    <CssReset />
    <slot />
</main>
<ButtonSection on:click={handleClickButton}/>

<style>
    main {
        width: 100%;
        height: 90vh;
        padding: 1rem;
        position: relative;
        background-color: #ECEFF1;
    }
</style>