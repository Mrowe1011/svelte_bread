<script>
	import {onMount, onDestroy} from 'svelte'
	const scrollNavBar = 60
	let show = false
	onMount(() => {
		window.onscroll = () => {
			if (window.scrollY < scrollNavBar) {
				show = true
			} else {
				show = false
			}
		}
	})
	

</script>

<nav class:scrolled={show}>
	
	<div class="navbar">
		<img class="navbar" src="brimfield.jpeg" alt="" >
		<a class="navitem" href="/">Menu</a>
		<a class="navitem" href="/">About</a>
		<a class="navitem" href="/">Gallery</a>
		<a class="navitem" href="/">Contact us</a>
		<a class="navitem" href="/">Gift Cards</a>
	</div>
		<div class="social">
			<a class="socials" href="/"><img class="socials" src="social/instagram.svg" alt=""></a>
			<a  class="socials" href="/"><img class="socials" src="social/twitter.svg" alt=""></a>
			<a class="socials" href="/"><img class="socials" src="social/facebook.svg" alt=""></a>
	</div>

</nav>

<style>
	.navbar {
		display: flex;
		align-items: center;

	}
	a {
		color: black;
		text-decoration: none;
		font-size: 1.5em;
		margin-left: 3%;
		font-family: "adobe-garamond-pro";
	}
	.scrolled {
		
		transform: translate(0,calc(-100% - 1rem))
	}
	.social {
		display: flex;
		margin-right: 5%;
		align-items: center;

	}
	.navitem {
		margin-left: 15%;
		flex-shrink: 0;
	}
	nav {
        background-color: rgba(255, 255, 255, 0.95);
		width: 100%;
		position: fixed;
		box-shadow: 0 -0.4rem 0.9rem 0.2rem rgb(0 0 0 / 50%);
		transition: 0.5s ease;
		z-index: 999;
		display: flex;
		justify-content: space-between;

	}

	img.navbar {
		height: 100px;
		padding-left: 2%;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		height: 200vh;
	}
	.socials {
		height: 50px;
		margin-right: 6%;
	}
</style>


<slot>

</slot>