<script>
    let newTitle = "";
    export let createFunc;
    const create = () => createFunc(newTitle);
</script>

<div class="row">
    <button class="circle-button" on:click={create}></button>
    <input bind:value={newTitle} type="text" name="title" id="title">
</div>