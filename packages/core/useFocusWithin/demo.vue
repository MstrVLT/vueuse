<script setup lang="ts">
import { useFocusWithin } from '@vueuse/core'
import { useTemplateRef } from 'vue'

const target = useTemplateRef<HTMLFormElement>('target')

const { focused } = useFocusWithin(target)
</script>

<template>
  <div class="flex flex-col items-center">
    <form
      ref="target"
      class="shadow bg-base border-main rounded max-w-96 mx-auto p-8"
    >
      <input type="text" placeholder="First Name">
      <input type="text" placeholder="Last Name">
      <input type="text" placeholder="Email">
      <input type="text" placeholder="Password">
    </form>
    <div mt2>
      Focus in form: <BooleanDisplay :value="focused" />
    </div>
  </div>
</template>
