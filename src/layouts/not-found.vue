<script setup lang="ts">
const router = useRouter()

const { t } = useI18n()

function goBack() {
  if (history.length > 1)
    router.back()
  else
    router.replace('/')
}
</script>

<template>
  <main py-20 text="center teal-700 dark:gray-200">
    <p text-4xl mb-4>
      <i i-carbon-warning inline-block />
    </p>
    <RouterView />
    <p flex justify-center mt-10>
      <TheButton @click="goBack">
        {{ t('button.back') }}
      </TheButton>
    </p>
  </main>
</template>
