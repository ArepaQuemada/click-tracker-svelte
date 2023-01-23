<script lang="ts">
    export let left: number;
    export let top: number;
</script>

<div class="circle" style="--left:{`${left}px`};--top:{`${top}px`}">
</div>

<style>
    .circle {
        width: 1rem;
        height: 1rem;
        border-radius: 50%;
        border: 1px solid black;
        position: absolute;
        left: var(--left);
        top: var(--top);
    }
</style>