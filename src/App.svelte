<script>
	import { onMount } from 'svelte';
	import Loader from './Loader.svelte';
	import Title from './Title.svelte';
	import NewBouquet from './NewBouquet.svelte';
	import Bouquet from './Bouquet.svelte';
	import Collection from './Collection.svelte';
	let bouquets = [];
	let promiseB = Promise.resolve([]);
	let promiseC = Promise.resolve([]);
	const proxyurl = "https://cors-anywhere.herokuapp.com/";

	async function loadAll(val) {
		let ans = await fetch(proxyurl + val)
		let json = await ans.json();
		  if(ans.ok)
		  	return json;
	}

	onMount(() => {
		promiseB = loadAll('https://desolate-everglades-62768.herokuapp.com/productlist');
		promiseC = loadAll('https://desolate-everglades-62768.herokuapp.com/collectionlist');
	});

</script>

<style>
	.container {
		margin: auto;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: stretch;
		flex-wrap: wrap;
		width: 42rem;
	}

	@media all and (max-width: 320px) {
		.container {
			flex-direction: column;
			align-items: center;
		}
	}

</style>

<div class="container">

	<Title name = {'Букеты'}/>

	{#await promiseB}
			<Loader/>
		{:then lists}
			{#each lists as list, i}
				{#if i === 0} 
					<NewBouquet {...list}/>
				{:else}
					<Bouquet {...list}/>
				{/if}
			{/each}	
		{:catch error}
			<p style="color: red">Ошибка загрузки данных о букетах: { error.message } </p>
	{/await}

	<Title name = {'Коллекции'}/>

	{#await promiseC}
			<Loader/>
		{:then lists}
			{#each lists as list, i}
				<Collection {...list}/>
			{/each}	
		{:catch error}
			<p style="color: red">Ошибка загрузки данных о коллекциях: { error.message } </p>
	{/await}
</div>