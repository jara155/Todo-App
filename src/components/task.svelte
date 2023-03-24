<script>
	export let title;
    export let removeTask;
    export let index;

    function remove() {
        removeTask(index)
    }

</script>

<div class="row">
    <button class="circle-button" on:click={remove}></button>
    <h1 class="row-label">{title}</h1>
</div>