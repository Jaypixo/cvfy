<script lang="ts" setup>
const localePath = useLocalePath()
</script>

<template>
  <h1>
    <NuxtLink
      :to="localePath('/')"
      class="bg-none font-bold text-fl-lg uppercase tracking-widest inline-flex items-center justify-center"
      active-class="bg-none"
    >
      <img
        src="/logo.svg"
        alt="Vitapix"
        class="h-10 hover:opacity-80 transition-opacity"
      >
    </NuxtLink>
  </h1>
</template>
