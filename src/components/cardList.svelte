<!-- ini adalah components cards yang warna-warni -->
<script lang="ts">
    import { createEventDispatcher } from "svelte";
    import ToDoCard from "./todoCard.svelte";

    export let cards, listName, type, bindValue, id: string;

    const dispatch = createEventDispatcher();

    function handlerAddCard() {
        cards = [...cards, { todo: bindValue }];
        dispatch("addCard", { todo: bindValue, listName });
        bindValue = "";
    }
</script>

<div class="column is-4">
    <div class="card has-background-{type}">
        <div class="card-header">
            <p class="card-header-title">{listName}</p>
        </div>
        <!-- isi konten cardnya -->
        <div class="card-content" {id}>
            {#each cards as card, index}
                <ToDoCard content={card.todo} {listName} {index} />
            {/each}
        </div>
        <div class="card-content">
            <input
                type="text"
                class="input is-primary"
                bind:value={bindValue}
            />
            <button
                on:click={handlerAddCard}
                class="button is-primary mt-2 mb-1">Add Task</button
            >
        </div>
    </div>
</div>
