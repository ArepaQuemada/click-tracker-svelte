<div class="button-section">
        <button on:click name="Undo">Undo</button>
        <button on:click name="Redo">Redo</button>
</div>

<style>
    .button-section {
        height: 10vh;
        display: flex;
        justify-content: space-around;
        align-items: center;
        background-color: #37474F;
        padding: 1rem;
    }
    button {
        all: unset;
        flex-basis: 25%;
        padding: .5rem;
        border-radius: 8px;
        background-color: #03A9F4;
        text-align: center;
        cursor: pointer;
        color: #FAFAFA;
        max-width: 450px;
    }
    button:hover {
        opacity: 0.5;
    }
</style>