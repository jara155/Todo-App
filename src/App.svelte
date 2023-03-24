<script>
	import TaskCreate from "./components/task-create.svelte";
	import Task from "./components/task.svelte";

	let tasks = [];
	let creating = false;

	function addTask(title) {
		tasks.push(title);
		tasks = tasks;
		handleCreating();
	}

	function removeTask(index) {
		tasks.splice(index, 1);
		tasks = tasks;
	}

	function handleCreating() {
		creating = !creating;
	}

</script>

<header>
	<div class="grid">
		<h1 class="list-label">Seznam nesplněných úkolů</h1>
		<button class="add-button" on:click={handleCreating}>+</button>
	</div>
</header>


<main class="list">
	{#if creating}		 
		<TaskCreate createFunc={addTask}></TaskCreate>
	{/if}
	{#each tasks as task, index}
		<Task title={task} {removeTask} {index}></Task>
	{/each}
</main>