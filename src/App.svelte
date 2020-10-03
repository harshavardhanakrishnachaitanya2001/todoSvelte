<script>
    let newItem = '';	
    let todoList = [];
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	function emptyList() {
		todoList=[];
		todoList = todoList;
	}
</script>

<div class='main'>
	<h1>Todo List with svelte</h1>
	<h2>Developed by: 'Harshavardhan'</h2>
	<b>Enter task:</b> <input bind:value={newItem} type="text">
	<button on:click={addToList} type='submit'>Add task</button><br/>
	{#each todoList as item, index}
		<input class='checking' bind:checked={item.status} type="checkbox">
		<span class:checked={item.status}>{item.text}</span>
		<br/>
	{/each}
	{
	todoList===[]?'':newItem
	}<br />
	<button on:click={emptyList}>Empty list</button>
</div>

<style> 
	.main{
		text-align:center;
	}
	.checking{
		cursor:pointer
	}
	.checked {
        text-decoration: line-through;
    }
	input{
		text-align:center;
	}
	button{
		cursor:pointer;
	}
</style> 