<script lang="ts">
	import { onMount } from "svelte"; // import lifecycle onMount dari svelte
	import dragula from "dragula"; // import dragulaJS
	import CardList from "./components/cardList.svelte"; // import components

	// list array of object
	let todo: string = [];
	let onGoing: string = [];
	let done: string = [];

	// variabel untuk menyimpan elementID, agar bisa dimasukkan ke function DragulaJS
	let ToDo: string;
	let OnGoing: string;
	let Done: string;

	// lifecycle onMount
	onMount(() => {
		ToDo = document.getElementById("todo");
		OnGoing = document.getElementById("ongoing");
		Done = document.getElementById("done");
		dragula([ToDo, OnGoing, Done], { removeOnSpill: true });
	});

	// fungsi buat ngehandle add card
	function eventHandlerAddCard(event) {
		let data: string = event.detail;

		if (data.listName == "To Do") {
			todo = [...todo, { todo: data.todo }];
		} else if (data.listName == "On Going") {
			onGoing = [...onGoing, { todo: data.todo }];
		} else {
			done = [...done, { todo: data.todo }];
		}
	}
</script>

<!-- tampilan utamanya  -->
<div class="container is-fluid">
	<br />
	<h1 class="is-size-3 has-text-centered">
		Simple Drag and Drop ToDo App <br /> with DragulaJS
	</h1>
	<br />
	<br />
	<br />

	<div class="columns">
		<!-- card todo  -->
		<CardList
			cards={todo}
			listName="To Do"
			type="danger-light"
			bindValue="Mencoba mencari pujaan hati di PT. Mencari Cinta Sejatich"
			on:addCard={eventHandlerAddCard}
			id="todo"
		/>
		<CardList
			cards={onGoing}
			listName="On Going"
			type="warning-light"
			bindValue="apalah"
			on:addCard={eventHandlerAddCard}
			id="ongoing"
		/>
		<CardList
			cards={done}
			listName="Done"
			type="primary-light"
			bindValue="hehe"
			on:addCard={eventHandlerAddCard}
			id="done"
		/>
	</div>
</div>

<!-- footernya  -->
<footer class="footer">
	<p class="has-text-centered">
		This Project Powered By <a href="https://svelte.dev/">Svelte</a> ,
		<a href="https://bulma.io/">Bulma</a> , and
		<a href="https://bevacqua.github.io/dragula/">DragulaJS</a>
	</p>
</footer>

<!-- stylenya -->
<style>
	.container {
		height: 90vh;
	}
</style>
