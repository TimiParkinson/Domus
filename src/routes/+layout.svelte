<script>
	let { children } = $props();
</script>

<nav>
	<a href="/">Domus</a>
	<div>
		<a href="/about">About</a>
		<a href="/contact">Contact</a>
		<a href="/sales">Sales</a>
	</div>
	<div>
		<a href="">Sign In</a>
		<a href="">Get Started</a>
	</div>
</nav>

{@render children()}

<style lang="scss">

</style>
