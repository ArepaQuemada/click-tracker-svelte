<script lang="ts">
    import Layout from '../layout/Layout.svelte'
    import Circle from '../components/Circle.svelte'
    
    import type {IPosition, ICircle} from '../interfaces'

    let circles: ICircle[] = []

    function handleAddCircle({detail: {x, y}}: CustomEvent<IPosition>) {
        circles = [...circles, {id: Math.random() * 10000, position: {x, y}}]
    }
    

</script>

<Layout on:add-circle={handleAddCircle}>
    {#each circles as circle}
        <Circle top={circle.position.y} left={circle.position.x} ></Circle>
    {/each}
</Layout>

<style>
    :root {
        margin: 0;
    }
</style>