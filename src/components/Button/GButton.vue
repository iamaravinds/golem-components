<template>
	<button type="button" class="
		p-3
		rounded-lg
		bg-orange-300
		text-white
		border-4
		border-indigo-500/100
		text-2xl
		font-semibold

		active:shadow-md
		active:shadow-gray-500

		hover:bg-orange-400
		hover:border-orange-500

		dark:border-4
		dark:border-indigo-500/100
		dark:bg-orange-400
		dark:active:bg-orange-500
		dark:active:shadow-md
		dark:active:shadow-gray-500

		transition-shadow
		transition-colors
		duration-200
		ease-linear
		" :class="{ 'w-full': props.expanded }">
		<slot />
	</button>
</template>

<script setup>
const props = defineProps({
	expanded: {
		type: Boolean,
		default: () => false,
	}
});
</script>
