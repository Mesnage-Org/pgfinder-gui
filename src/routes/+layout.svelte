<script lang="ts">
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import { AppShell, AppBar, storePopup } from '@skeletonlabs/skeleton';
	import Fa from 'svelte-fa/src/fa.svelte';
	import { faBars } from '@fortawesome/free-solid-svg-icons';
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead"><Fa icon={faBars} /></svelte:fragment>
			<strong class="text-xl">PGFinder</strong>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/Mesnage-Org/pgfinder"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
	<svelte:fragment slot="footer">
		<div class="flex justify-center">
			<p class="text-center w-full">
				Any issues or suggestions? Please get in touch!<br />
				<a href="mailto:smesnage@sheffield.ac.uk"
					><strong class="">smesnage@sheffield.ac.uk</strong></a
				>
			</p>
		</div>
	</svelte:fragment>
</AppShell>
