<script lang="ts">
    import Layout from '../layout/Layout.svelte'
    import Circle from '../components/Circle.svelte'
    
    import type {IPosition, ICircle} from '../interfaces'

    let circles: ICircle[] = []

    $: circlesToShow = circles.slice(0, pointer)
    let pointer = 0

    function handleAddCircle({ detail: { x, y }}: CustomEvent<IPosition>) {
        if (circlesToShow.length !== circles.length) return
        circles = [...circles, {id: new Date().getTime(), position: {x, y}}]
        pointer ++
    }

    function handleButtonClick ({ detail: { action }}: CustomEvent<{action: "Undo" | "Redo"}>){
        if (action === 'Undo') {
            pointer = circlesToShow.length !== 0 ? pointer - 1 : pointer
        } else {
            pointer = circlesToShow.length !== circles.length ? pointer + 1 : pointer 
        }
    }

    $: if(pointer < 0) {
        pointer = 0
    }
    
</script>

<Layout on:add-circle={handleAddCircle} on:action-button={handleButtonClick}>
    {#each circlesToShow as circle}
        <Circle top={circle.position.y} left={circle.position.x} ></Circle>
    {/each}
</Layout>

<style>
    :root {
        margin: 0;
    }
</style>