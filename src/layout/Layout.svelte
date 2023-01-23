
<script lang="ts">
    /**
     * TODO
     * AGREGAR FUNCIONALIDAD DE AGREGAR Y ELIMINAR CIRCULOS (AVANZAR EL PUNTERO)
     * DESEABLE: HABILITAR Y DESHABILITAR BOTON SI NO SE PUEDE RETROCEDER O AVANZAR MÁS
     * 
     * MEJORA: VARIABLE HISTORY QUE TIENE TODOS LOS CIRCULOS
     * VARIABLE REACTIVA PARA RENDERIZAR
     * 
     * MEJORAR ESTILOS ESTÁN HORRIBLES
    */
	import { createEventDispatcher } from "svelte";
	import ButtonSection from "../components/ButtonSection.svelte";
	import CssReset from "../css-reset/CssReset.svelte";
    
    const dispatch = createEventDispatcher()

    function handleClick(e: MouseEvent){
        dispatch('add-circle', {
            x: e.clientX,
            y: e.clientY
        })
    }

</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<main on:click={handleClick}>
    <CssReset />
    <slot />
</main>
<ButtonSection />

<style>
    main {
        width: 100%;
        height: 90vh;
        padding: 1rem;
        position: relative;
    }
</style>