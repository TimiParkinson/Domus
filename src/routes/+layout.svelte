<script>
	let { children } = $props();
</script>

<div class="app-container">
	<nav>
		<a href="/" class="logo">Domus</a>
		<div class="nav-links">
			<a href="/about">About</a>
			<a href="/contact">Contact</a>
			<a href="/sales">Sales</a>
		</div>
		<div class="nav-actions">
			<a href="" class="sign-in">Sign In</a>
			<a href="" class="get-started">Get Started</a>
		</div>
	</nav>

	<main>
		{@render children()}
	</main>
</div>

<style lang="scss">
	:global(*) {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
	:global(body, html) {
		height: 100%;
        width: 100%;
		position: fixed;
        margin: 0;
        padding: 0;
        background-color: #121212;
        color: #ffffff;
    }

.app-container {
	display: flex;
	flex-direction: column;
	height: 100vh;
	background-color: #121212;
}

nav {
	display: flex;
	align-items: center;
	justify-content: space-between;
	background-color: #1e1e1e;
	color: #ffffff;
	padding: 1rem 2rem;
	flex-shrink: 0;

	.logo {
		color: #ffffff;
		font-size: 1.5rem;
		font-weight: bold;
		text-decoration: none;
	}

	.nav-links {
		display: flex;
		gap: 1.5rem;

		a {
			color: #b0b0b0;
			text-decoration: none;
			transition: color 0.3s ease;

			&:hover {
				color: #ffffff;
			}
		}
	}

	.nav-actions {
		display: flex;
		gap: 1rem;

		.sign-in {
			color: #b0b0b0;
			text-decoration: none;
			padding: 0.5rem 1rem;
			border: 1px solid #333;
			border-radius: 4px;
			transition: all 0.3s ease;

			&:hover {
				background-color: #333;
				color: #ffffff;
			}
		}

		.get-started {
			background-color: #4CAF50;
			color: white;
			text-decoration: none;
			padding: 0.5rem 1rem;
			border-radius: 4px;
			transition: background-color 0.3s ease;

			&:hover {
				background-color: #45a049;
			}
		}
	}
}

main {
	flex-grow: 1;
	overflow-y: auto;
	background-color: #121212;
}
</style>