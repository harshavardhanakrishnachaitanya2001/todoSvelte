<script>
	let thing='';
	let listOfThings=[];
	function handleChange(e){
		e.preventDefault();
		thing=e.target.value;
	}
	function handleClick(e){
		e.preventDefault();
		listOfThings.push(thing);
		listOfThings=listOfThings;
		thing='';
	}
	
</script>
<div>
	<h1>Todo application</h1>
	<h2>Made by: G. Harshavardhan</h2>
	<b>task:</b> <input type='text' placeholder='task name' on:change={handleChange} value={thing} required/>
	<button on:click={handleClick}>Add task</button>
	<p class='displayListOfThings'>{listOfThings}</p>
</div>

<style>
	div {
		text-align: center;
	}
	button{
		cursor:pointer
	}
	input{
		text-align: center;
	}

	h1 {
		font-size: 4em;
		font-weight: bolder;
	}
</style>