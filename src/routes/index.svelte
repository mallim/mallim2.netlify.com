<script>
	import { onMount } from "svelte";

	onMount(() => {
		if (window.netlifyIdentity) {
			window.netlifyIdentity.on("init", (user) => {
				if (!user) {
					window.netlifyIdentity.on("login", () => {
						document.location.href = "/admin/";
					});
				}
			});
		}
	});
</script>

<svelte:head>
	<title>Sapper project template</title>
	<script
		src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
</svelte:head>

<h1>Welcome to SvelteKit</h1>
<p>
	Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>
<p><a sveltekit:prefetch href="/blog">Click here</a> to see the blog</p>
