<script>
    export let title;
    export let content;
</script>

<div>
    <h1>{title}</h1>
    <p>{content}</p>
</div>

<style scoped>
    div {
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 1rem;
        border: 1px solid black;
        border-radius: 16px;
    }
</style>