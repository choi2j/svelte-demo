<script>
    import Card from "./lib/Card.svelte";
    import ColorChange from "./lib/ColorChange.svelte";
    import Counter from "./lib/Counter.svelte";

    const items = [
        { title: "김지민 바보", content: "이건 부정할 수 없는 사실" },
        { title: "해커톤 왜 함", content: "이거 할 바에 코드페어" },
        { title: "이이잉", content: "시험 공부하러 감 ㅅㄱㅇ" },
    ];

    let color = "#ffffff";

    let text = "";

    let todoList = [];

    function addToList() {
        todoList = [...todoList, text];
        text = "";
    }
</script>

<main>
    {#each items as item}
        <Card title={item.title} content={item.title} />
    {/each}
    <div>
        <input type="color" bind:value={color} />
        <ColorChange {color} />
    </div>
    <div>
        <Counter />
    </div>
    <div class="list">
        <div>
            <input bind:value={text} type="text" />
            <button on:click={addToList}>Add</button>
        </div>
        {#each todoList as todo}
            <p>{todo}</p>
        {/each}
    </div>
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        padding: 2rem;
    }

    div {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1rem;
    }

    .list {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        gap: 1rem;
    }
</style>
