<script lang="ts">
	import { t } from '$lib/translations';
	import * as Alert from '$lib/components/ui/alert';
	import { Info } from 'lucide-svelte';

	export let currentVersion: string;
	export let newVersionInfo: { version: string; description: string; url: string } | null = null;
</script>

<footer class="bg-muted py-6 md:py-0">
	<div class="container mx-auto flex flex-col items-center justify-center gap-4 py-8 md:flex-row">
		<div class="flex flex-col items-center gap-2">
			{#if newVersionInfo}
				
			{/if}
			<p class="text-balance text-center text-xs font-medium leading-loose">
				© {new Date().getFullYear()}
				<a href="https://archiv.pollhammer.org/" target="_blank">Manuel Pollhammer</a>. {$t(
					'app.components.footer.all_rights_reserved'
				)}
			</p>
			<p class="text-balance text-center text-xs font-medium leading-loose">
				Version: 1.0
			</p>
		</div>
	</div>
</footer>
