<template>
  <div>
    <div class="py-4" />

    <input
      v-model="name"
      :placeholder="t('intro.whats-your-name')"
      class="px-4 py-2 text-sm text-center bg-transparent border border-gray-200 rounded outline-none active:outline-none dark:border-gray-700"
      style="width: 250px"
      @keydown.enter="go"
    >

    <div>
      <button
        class="m-3 text-sm btn"
        :disabled="!name"
        @click="go"
      >
        {{ t('button.go') }}
      </button>
    </div>
  </div>
</template>

<script setup lang='ts'>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useI18n } from 'vue-i18n'

export const name = ref('')

const router = useRouter()
export const go = () => {
  if (name.value)
    router.push(`/hi/${name.value}`)
}

const { t } = useI18n()
export { t }
</script>
