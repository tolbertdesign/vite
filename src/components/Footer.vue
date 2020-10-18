<template>
  <div class="mt-6 text-xl">
    <div class="mx-2 icon-btn" @click="isDark = !isDark">
      <Icon :icon="isDark ? 'carbon:moon' : 'carbon:sun'" class="inline-block" />
    </div>

    <div class="mx-2 icon-btn" @click="toggleLocales">
      <Icon icon="carbon:language" class="inline-block" />
    </div>
  </div>
</template>

<script setup lang='ts'>
import { useI18n } from 'vue-i18n'
import { locales } from '/~/messages'
export { isDark } from '/~/utils'

const i18n = useI18n()

export const toggleLocales = () => {
  // change to some real logic
  i18n.locale.value = locales[(locales.indexOf(i18n.locale.value) + 1) % locales.length]
}
</script>
