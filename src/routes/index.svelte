<script>
	import { Router, Route, Link } from 'svelte-routing';
	import About from './about.svelte';
	import Home from './home.svelte';
	import Product from './product.svelte';
	import Products from './products.svelte';
</script>

<Router>
	<header>
		<nav>
			<Link to="/">Home</Link>
			<Link to="products">Products</Link>
			<Link to="about">About</Link>
		</nav>
	</header>

	<div>
		<Route path="/" component={Home} />
		<Route path="products" component={Products} />
		<Route path="products/:id" component={Product} />
		<Route path="about" component={About} />
	</div>
</Router>

<!-- https://api.artic.edu/api/v1/artworks -->
