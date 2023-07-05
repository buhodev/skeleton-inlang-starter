<script lang="ts">
	import { languages, switchLanguage } from '@inlang/sdk-js';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Skeleton + Inlang</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				{#each languages as lang}
					<button class="btn btn-sm variant-ghost-surface" on:click={() => switchLanguage(lang)}>
						{lang === 'en' ? 'English' : 'German'}
					</button>
				{/each}
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
