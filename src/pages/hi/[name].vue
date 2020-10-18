
<template>
  <div>
    <p class="text-4xl">
      <Icon class="inline-block iconify" icon="carbon:pedestrian" />
    </p>
    <p>
      {{ t('intro.hi', {name}) }}
    </p>
    <p class="text-sm opacity-50">
      <em>{{ t('intro.dynamic-route') }}</em>
    </p>

    <div>
      <button
        class="m-3 mt-8 text-sm btn"
        @click="back"
      >
        {{ t('button.back') }}
      </button>
    </div>
  </div>
</template>

<script setup='props' lang='ts'>
import { useRouter } from 'vue-router'
import { useI18n } from 'vue-i18n'

declare const props: {
  name: string
}

const router = useRouter()
export const back = () => router.push('/')

const { t } = useI18n()
export { t }
</script>
