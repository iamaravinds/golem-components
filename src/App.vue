<script setup>
import GButton from "@/components/Button/GButton.vue";
import GInput from "@/components/InputBox/GInput.vue";
import GSearch from "@/components/SearchBox/GSearch.vue";

function alertItem(value) {
  alert(`You have selected Category ${value.category || 'empty'} and searched ${value.searchText || 'empty'}`);
}
</script>

<template>
  <div class="
    m-auto
    w-1/2
    mt-20
    h-auto
    dark:border-2
    dark:rounded-md
    dark:border-gray-200
    p-20">
    <GButton>
      Click me 🐷
    </GButton>
    <GButton expanded>
      I am Fat 🐷
    </GButton>
    <GInput />
    <GInput placeholder='Secret here!! 🤫' type="password" />
    <GSearch
    @search='alertItem'
    />
    <GSearch
      :category="[
        'Pokemon',
        'Dragon Ball Z',
        'Naruto',
      ]"
      @search='alertItem'
    />
  </div>

</template>

<style scoped>
</style>
