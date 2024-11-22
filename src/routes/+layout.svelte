<script>
	let { children } = $props();
</script>

<nav>
	<a href="/">Domus</a>
	<a href="/about">About</a>
    <a href="/contact">Contact</a>
	<a href="/sales">Sales</a>
</nav>

{@render children()}
