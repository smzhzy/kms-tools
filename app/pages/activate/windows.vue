<script setup lang="ts">
definePageMeta({
  title: 'pages.activate.title.windows',
})

function generateScript(formData: ActivateFormData) {
  const { host, license } = formData
  return (
    `@echo off\r\n` +
    `slmgr /skms ${host}\r\n` +
    `slmgr /ipk ${license}\r\n` +
    `slmgr /ato\r\n` +
    `slmgr /xpr`
  )
}
</script>

<template>
  <CommonActivate
    title="Windows"
    :gvlksData="WINDOWS_GVLKS"
    :generateScript
  ></CommonActivate>
  <CommonTips></CommonTips>
</template>
