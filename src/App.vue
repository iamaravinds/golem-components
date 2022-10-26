<script setup>
import GButton from "@/components/Button/GButton.vue";
import GInput from "@/components/InputBox/GInput.vue";
</script>

<template>
  <div class="
    m-auto
    w-1/2
    mt-20
    h-96
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
  </div>

</template>

<style scoped>

</style>
