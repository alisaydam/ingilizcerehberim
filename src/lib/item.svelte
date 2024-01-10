<script>
	import { getContext } from 'svelte';

	import { slide } from 'svelte/transition';

	export let id;

	export let title;

	export let subTitle = '';

	let isHovered = false;

	let isFocused = false;

	const active = getContext('context');

	$: isCurrentActive = $active === id;

	const onClickHandler = () => {
		if (isCurrentActive) {
			$active = null;
		} else {
			$active = id;
		}
	};
</script>

<div
	class="
    border-gray-100
    border-2
    rounded-sm
"
>
	<button
		on:click={onClickHandler}
		on:mouseenter={() => (isHovered = true)}
		on:mouseleave={() => (isHovered = false)}
		on:focus={() => (isFocused = true)}
		on:blur={() => (isFocused = false)}
		class="flex text-left w-full focus:outline-none items-center p-4"
	>
		<div class="w-full">
			<div
				class="
                font-bold
                text-sm
                mb-1
                transition
                text-gray-700
            "
				class:text-blue-400={isHovered || isFocused}
			></div>
			{#if !!subTitle}
				<div class="text-gray-500 text-sm">
					{subTitle}
				</div>
			{/if}
		</div>

		<div
			class="
            w-8
            transform
            transition
            text-gray-300
        "
			class:rotate-180={isCurrentActive}
			class:text-blue-400={isHovered || isFocused}
		>
			<p class="arrow">˅</p>
		</div>
	</button>

	{#if isCurrentActive}
		<div class="px-4 pb-4 mt-4" transition:slide>
			<slot />
		</div>
	{/if}
</div>

<style>
	.arrow {
		text-align: center;
	}
</style>
