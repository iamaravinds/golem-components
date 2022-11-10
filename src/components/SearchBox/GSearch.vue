<template>
	<form>
		<label for="default-search" class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search</label>
		<div
			class='
				p-3
				rounded-lg
				bg-orange-100
				text-black
				border-4
				dark:border-4
				dark:border-indigo-500/100
				dark:bg-orange-100
				border-indigo-500/100
				hover:bg-orange-200
				hover:border-orange-500
				hover:dark:text-gray-900
				dark:active:shadow-md
				dark:active:shadow-gray-500
				transition-shadow
				duration-200
				relative'
		>
			<div class='flex'>
				<button
					v-if='category.length'
					id="dropdown-button"
					class='
						flex-shrink-0
						z-10
						inline-flex
						items-center
						py-2.5
						px-4
						text-center
						m-2
						p-2
						text-l
						font-semibold
						outline-0
						bg-inherit'
					type="button"
					@click='dropdownClicked'
					>
					{{getSelectedCategory}}
					<svg aria-hidden="true" class="ml-1 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg" data-darkreader-inline-fill="" style="--darkreader-inline-fill:currentColor;">
						<path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd">
					</path>
				</svg>
			</button>
			<div
				v-if='category.length'
				id="dropdown"
				:class="{
					'hidden': !isdropdownClicked
				}"
				class="z-20 w-44 bg-white rounded divide-y divide-gray-100 shadow bg-inherit text-black" data-popper-reference-hidden="" data-popper-escaped="" data-popper-placement="bottom" style="position: absolute; inset: 0px auto auto 0px; margin: 0px; transform: translate3d(0px, 10px, 0px);"
			>
					<ul class="py-1 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdown-button">
						<li @click='dropdownClicked(false)' v-for='(item, index) in category' :key='index'>
							<button 
								type="button"
								class="
									inline-flex
									py-2
									px-4
									w-full
									bg-inherit
									text-xl
									font-semibold
									text-black
									border-4
									dark:border-2
									dark:border-indigo-300
									dark:bg-orange-100
									hover:bg-orange-200
									hover:border-orange-500
									hover:dark:text-gray-900
									"
								@click='selectCategory(item)'
							>
								{{item}}
							</button>
						</li>
					</ul>
			</div>
			<svg v-if='!category.length'
				aria-hidden="true"
				class="w-14 h-14 text-gray-800 dark:text-gray-800" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" data-darkreader-inline-stroke="" style="--darkreader-inline-stroke:currentColor;"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
			<input
				type="text"
				id='default-search'
				:placeholder="placeholder"
				required
				v-model='searchText'
				class='
					m-2
					p-2
					text-2xl
					font-semibold
					w-full
					outline-0
					bg-inherit
					'
				>
			<button 
				type="button" 
				@click='search'
				class="
				p-1
				m-auto
				text-center
				rounded-lg
				bg-orange-300
				text-white
				border-2
				h-10
				border-indigo-500/100
				text-l
				font-semibold

				active:shadow-md
				active:shadow-gray-500

				dark:border-2
				dark:border-indigo-500/100
				dark:bg-orange-400
				dark:active:bg-orange-500
				dark:active:shadow-md
				dark:active:shadow-gray-500

				transition-shadow
				duration-200
				ease-linear
				">
				Search
			</button>
			</div>
		</div>
	</form>
</template>

<script setup>
import { computed } from '@vue/reactivity';
import { ref } from 'vue';

const emit = defineEmits(['search'])
const { placeholder, category, defaultCategoryPlaceholder } = defineProps({
	placeholder: {
		type: String,
		default: () => 'Start Typing',
	},
	category: {
		type: Array,
		default: () => [],
	},
	defaultCategoryPlaceholder: {
		type: String,
		default: () => 'Select Category',
	}
});
const selectedCategory = ref('');
const isdropdownClicked = ref(false);
const searchText = ref('');
const getSelectedCategory = computed(() => selectedCategory.value || defaultCategoryPlaceholder);

function search() {
  emit('search', {
		category: selectedCategory.value,
		searchText: searchText.value
	});
}

function dropdownClicked(value) {
	if (value === false) {
		isdropdownClicked.value = false;
	} else {
		isdropdownClicked.value = !isdropdownClicked.value;
	}
}

function selectCategory(value) {
	dropdownClicked(false);
	return selectedCategory.value = value;
}
</script>
