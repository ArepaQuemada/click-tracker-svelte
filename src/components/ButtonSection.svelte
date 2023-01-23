<div class="button-section">
        <button>Undo</button>
        <button>redo</button>
</div>

<style>
    .button-section {
        height: 10vh;
        display: flex;
        justify-content: space-around;
        align-items: center;
        background-color: grey;
        padding: 1rem;
    }
    button {
        all: unset;
        flex-basis: 25%;
        padding: .5rem;
        border-radius: 8px;
        background-color: aqua;
        text-align: center;
        cursor: pointer;
    }
</style>