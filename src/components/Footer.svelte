<script>
	import { Icon, LocaleSelector } from '$comp';
	import { t } from '$lib/translations';

	const followLinks = [
		{ url: 'https://twitter.com/coinoswallet', titleID: 'twitter' },
		{ url: 'https://github.com/coinos', titleID: 'github' },
		{ url: 'https://t.me/coinoswallet', titleID: 'telegram' }
	];

	const companyLinks = [
		{ url: '/news', titleID: 'news' },
		{ url: '/support', titleID: 'support' },
		{ url: '/jobs', titleID: 'jobs' }
	];
</script>

<footer class="space-y-10 md:space-y-0 text-xl block md:flex justify-around items-center mb-20">
	<div>
		<div class="text-center w-full mb-8">
			<a href="/"><Icon icon="logo" style="w-48 mx-auto md:mx-0" /></a>
		</div>
		<div class="flex gap-2 justify-center">
			<div>
				<a href="/register">
					<button
						class="bg-black text-white border rounded-full px-6 py-4 font-bold hover:opacity-80 text-lg"
					>
						{$t('nav.startInSeconds')}
					</button>
				</a>
			</div>
			<LocaleSelector style="p-2 rounded-md text-center hover:opacity-80 cursor-pointer" />
		</div>
	</div>

	<div class="text-center md:text-left">
		<p class="font-semibold">{$t('footer.followUs')}</p>
		<ul class="mt-5 text-secondary space-y-3 font-medium">
			{#each followLinks as link}
				<li>
					<a href={link.url} target="_blank" rel="noreferrer" class="hover:opacity-80"
						>{$t('footer.' + link.titleID)}</a
					>
				</li>
			{/each}
		</ul>
	</div>

	<div class="text-center md:text-left">
		<p class="font-semibold">{$t('footer.company')}</p>
		<ul class="mt-5 text-secondary space-y-3">
			{#each companyLinks as link}
				<li><a href={link.url} class="hover:opacity-80">{$t('footer.' + link.titleID)}</a></li>
			{/each}
		</ul>
	</div>

	<Icon icon="shield" style="mx-auto md:mx-0" />
</footer>
