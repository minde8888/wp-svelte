<script>
	export let segment
	export let menuItems
</script>

<style>
	nav {
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	.selected {
		position: relative;
		display: inline-block;
	}

	.selected::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<nav>
	<ul>
		{#each menuItems.items as item}
			<li><a
					class:selected='{item.slug === "home" ? segment === undefined : segment === item.slug}'
					href='{ item.slug === "home" ? "." : item.slug}'>
				{item.title}
			</a>
			</li>
		{/each}
		<!--<li><a class:selected='{segment === undefined}' href='.'>home</a></li>
		<li><a class:selected='{segment === "about"}' href='about'>about</a></li>
		<li><a rel=prefetch class:selected='{segment === "blog"}' href='blog'>blog</a></li>-->
	</ul>
</nav>
