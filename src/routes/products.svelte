<script>
	import { Link, Route, Router } from 'svelte-routing';
	import { onMount } from 'svelte';
	let items = [];

	onMount(async () => {
		const response = await fetch('https://fakestoreapi.com/products/category/electronics');
		items = await response.json();
		console.log(items);
	});
</script>

<h1>Products</h1>

<Router>
	<ul class="item-list">
		{#each items as item}
			<li>
				<div class="img">
					<img src={item.image} alt="" />
				</div>
				<Link class="test" to={'' + item.id}>
					{item.title}
				</Link>
			</li>
		{/each}
	</ul>
</Router>

<style>
	.item-list {
		display: flex;
		flex-wrap: wrap;
		margin-left: -1em;
		margin-bottom: -1em;
	}

	.img {
		padding: 1em;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100%;
	}

	.item-list li {
		width: calc(33.333% - 1em);
		margin-left: 1em;
		margin-bottom: 1em;
		display: flex;
		justify-content: space-between;
		flex-direction: column;
	}

	.item-list li img {
		display: block;
		width: 100%;
		height: 100%;
		object-fit: contain;
	}
</style>
