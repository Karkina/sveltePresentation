<script>
    export let tasks;
    export let description;
    export let type;
</script>

<table>
    <thead>
        <tr>
            <th>ID</th>
            <th>Basic</th>
            <th>Emergency</th>
            <th>ToDo</th>
        </tr>
    </thead>
    <tbody>
        {#each tasks as task (task.id)}
            <tr>
                <td>{task.id}</td>
                {#if task.type === "basic"}
                    <td>{task.name}</td>
                    <td>-</td>
                    <td>-</td>
                {:else if task.type === "emergency"}
                    <td>-</td>
                    <td>{task.name}</td>
                    <td>-</td>
                {:else}
                    <td>-</td>
                    <td>-</td>
                    <td>{task.name}</td>
                {/if}
            </tr>
        {/each}
    </tbody>
</table>

<style>
    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 20px;
    }

    th,
    td {
        padding: 10px;
        text-align: left;
        border-bottom: 1px solid #ccc;
    }

    th {
        background-color: #f2f2f2;
    }

    td {
        background-color: #fff;
    }

    tr:nth-child(even) td {
        background-color: #f9f9f9;
    }

    .type-basic {
        background-color: #c7ecee;
    }

    .type-emergency {
        background-color: #ff7675;
    }

    .type-todo {
        background-color: #74b9ff;
    }
</style>
