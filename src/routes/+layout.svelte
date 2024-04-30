<script lang="ts">
	import { fade } from 'svelte/transition';
	export let data;
	const transitionSpeed = 250 / 2;
</script>

<nav>
	<ul>
		<li>
			<a href="/">home</a>
		</li>
		<li>
			<a href="/about">about</a>
		</li>
	</ul>
</nav>
{#key data}
	<div
		in:fade={{ duration: transitionSpeed, delay: transitionSpeed + 250 }}
		out:fade={{ duration: transitionSpeed }}
	>
		{data.url}
		<slot />
	</div>
{/key}
