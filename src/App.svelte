<script lang="ts">
	import { Router, Route, Link } from "svelte-routing";
	import { onMount } from "svelte";
	import { fade } from "svelte/transition";
	import NavLink from "./components/NavLink.svelte";
	import Home from "./routes/Home.svelte";
	import Faq from "./routes/Faq.svelte";
	import Confirm from "./routes/Confirm.svelte";
	import Reset from "./routes/Reset.svelte";
</script>

<Router>
	<main>
		<logo>
			<Link to="/">
				<logoLink>
					<img
						height="50"
						width="50"
						alt=""
						src="logo.svg"
						style="margin-right:10px;border:1px solid #ffffff;"
					/>
					productabot
				</logoLink>
			</Link>
			<nav>
				<NavLink to="/">home</NavLink> |
				<NavLink to="/faq">faq</NavLink> |
				<a
					class="link"
					target="_blank"
					href="https://github.com/productabot">github</a
				>
				|
				<a
					class="link not-mobile"
					target="_blank"
					href="https://app.productabot.com/login?demo=true">demo</a
				>
				<a
					class="link only-mobile"
					target="_blank"
					href="javascript:alert(`In order to demo, make sure you've installed the app first`);window.open(`productabot://demo`)"
					>demo</a
				>
				|
				<a
					class="link not-mobile"
					style="background-color:#3F0054;padding:5px 10px;"
					href="https://app.productabot.com/login">login</a
				>
				<a
					class="link not-mobile"
					style="background-color:#3F91A1;padding:5px 10px;"
					href="https://app.productabot.com/signup">signup</a
				>
				<a
					class="link only-mobile"
					style="background-color:#3F91A1;padding:5px 10px;"
					href="javascript:alert(`Sorry, this app isn't available for mobile devices yet. Visit this page on desktop instead!`)"
					>download app</a
				>
			</nav>
		</logo>
		<Route path="/" component={Home} />
		<Route path="faq" component={Faq} />
		<Route path="confirm" component={Confirm} />
		<Route path="reset" component={Reset} />
	</main>
	<footer>© {new Date().getFullYear()} productabot</footer>
</Router>

<style>
	main {
		margin: auto;
		max-width: 800px;
		min-height: calc(100vh - 100px);
	}
	logo {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}
	logoLink {
		cursor: pointer;
		display: flex;
		flex-direction: row;
		align-items: center;
		font-size: 50px;
		font-weight: 100;
		pointer-events: none;
		transform: none;
	}
	footer {
		padding: 20px;
		color: #aaaaaa;
		font-size: 10px;
		text-align: center;
	}
	nav {
		color: #444444;
	}
	@media (max-width: 640px) {
		main {
			max-width: 100%;
		}
		footer {
			width: unset;
		}
		logo {
			flex-direction: column;
		}
		nav {
			margin-top: 10px;
		}
	}
</style>
