<!-- ini adalah components cards yang bisa di drag and drop -->
<script lang="ts">
    import { slide } from "svelte/transition";
    export let content, listName: string;
    export let index;
</script>

<div
    class=" card mb-3 has-background-primary-light"
    draggable="true"
    transition:slide
>
    <div class="card-content">
        <div class="columns">
            <div class="column is-9">
                <p class="has-text-primary-dark">{content}</p>
            </div>
        </div>
    </div>
</div>

<style>
</style>
