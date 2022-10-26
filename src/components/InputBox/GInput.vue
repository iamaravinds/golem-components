<template>
	<input :type="type" class="
		p-3
		rounded-lg
		bg-orange-100
		text-black
		border-4
		border-indigo-500/100
		text-2xl
		font-semibold

		active:shadow-md
		active:shadow-gray-500

		hover:bg-orange-200
		hover:border-orange-500

		dark:hover:text-gray-100
		dark:border-4
		dark:border-indigo-500/100
		dark:bg-orange-100
		dark:active:shadow-md
		dark:active:shadow-gray-500

		transition-shadow
		transition-colors
		duration-200
		ease-linear
		" :class="{ 'w-full': props.expanded }" :placeholder="placeholder" />
</template>

<script setup>
const props = defineProps({
	expanded: {
		type: Boolean,
		default: () => false,
	},
	type: {
		type: String,
		default: () => 'text',
	},
	placeholder: {
		type: String,
		default: () => 'Start Typing',
	}
});
</script>
