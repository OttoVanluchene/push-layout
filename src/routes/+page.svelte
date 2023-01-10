<script>
    let counter = 1;
    let grid = new Array(8);
    for (let i = 0; i < 8; i++) {
        grid[i] = new Array(8);
        for (let j = 0; j < 8; j++) {
            grid[i][j] = counter;
            counter++;
        }
    }
</script>

<div class="grid">
    {#each grid as row, rowIndex}
        {#each row as cell, colIndex}
            <div class="grid-item" style="order: {(8 * (7 - rowIndex) + (colIndex + 1))}">
                <span>{cell}</span>
            </div>
        {/each}
    {/each}
</div>

<style>
    .grid {
        display: grid;
        grid-template-columns: repeat(8, 1fr);
        grid-template-rows: repeat(8, 1fr);
        grid-template-rows: reverse;
        grid-gap: 5px;
        width: calc(60px * 8 + 5px * 7);
        height: calc(50px * 8 + 5px * 7);
    }
    .grid-item {
        background-color: #ccc;
        border: 1px solid #aaa;
        border-radius: 5px;
        height: 50px;
        width: 60px;
    }
    .grid-item:hover {
        background-color: rgb(100, 185, 241);
    }
</style>