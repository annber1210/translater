<button
	class="
		px-3
		py-1
		inline-flex
		items-center
		justify-start
		whitespace-nowrap
		rounded-full
		select-none
		{small ? 'text-sm' : 'text-base'}
		text-gray-900
		dark:text-gray-200
		{active ? 'bg-sky-200 dark:bg-sky-900' : 'hover:bg-gray-900/10 dark:hover:bg-white/10'}
		transition-all
		{className}
	"
	type="button"
	on:click
>
	{#if icon}
		<span class="mr-2">
			<Icon d={icon} />
		</span>
	{/if}
	{#if iconRaw}
		<span class="mr-2">
			<!-- eslint-disable-next-line svelte/no-at-html-tags -->
			{@html iconRaw}
		</span>
	{/if}
	<span>{label}</span>
	<slot />
	{#if iconRight}
		<span class="ml-2">
			<Icon d={icon} />
		</span>
	{/if}
</button>

<script>
import Icon from '~/lib/Icon.svelte';

export let label = '';
export let active = false;
export let small = false;
export let icon = '';
export let iconRight = '';
export let iconRaw = '';

let className = '';
export { className as class };
</script>
