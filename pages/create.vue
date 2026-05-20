<script setup lang="ts">
import { useCvState } from '~/data/useCvState'

const VITAPIX_IMAGE = '/logo.svg'

const { setUpCvSettings } = useCvState()
const route = useRoute()
const { t, locale } = useI18n()

const href = `https://vitapix.dev${route.path}`

onMounted(() => {
  setUpCvSettings()
})

useHead({
  htmlAttrs: {
    lang: locale,
  },
  title: t('title-tag'),
  link: [
    {
      rel: 'preload',
      as: 'image',
      href: 'https://cdn.ko-fi.com/cdn/kofi5.png?v=3',
    },
    {
      rel: 'canonical',
      href,
    },
  ],
  meta: [
    {
      name: 'description',
      content: t('description'),
    },
    {
      name: 'author',
      content: 'Jaypix',
    },
    {
      property: 'og:image',
      content: VITAPIX_IMAGE,
    },
    {
      property: 'og:author',
      content: 'Jaypix',
    },
    {
      property: 'og:title',
      content: t('title-tag'),
    },
    {
      property: 'og:description',
      content: t('description'),
    },
    {
      name: 'twitter:creator',
      content: 'Jaypix',
    },
    {
      name: 'twitter:title',
      content: t('title-tag'),
    },
    {
      name: 'twitter:url',
      content: href,
    },
    {
      name: 'twitter:description',
      content: t('description'),
    },
    {
      name: 'twitter:card',
      content: 'summary_large_image',
    },
    {
      name: 'twitter:image',
      content: CVFY_IMAGE,
    },
    {
      name: 'twitter:image:alt',
      content: t('description'),
    },
  ],
})
</script>

<template>
  <main class="font-app main">
    <CvSettings class="basis-1/4 min-w-80" />
    <CvPreview class="basis-3/4" />
  </main>
</template>

<style lang="postcss">
@import '@/assets/styles/form.postcss';
@media screen and (min-width: 1024px) {
  .main {
    @apply flex h-screen overflow-hidden;
  }
}
</style>
