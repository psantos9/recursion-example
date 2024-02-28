<template>
  <div class="h-screen flex flex-col items-center justify-center">
    <v-card :item="item"/>
  </div>
</template>

<script lang="ts" setup>
import VCard from '@/components/VCard.vue'
import type { IEntity } from '@/types';

const item: IEntity = {
  name: 'first item',
  children: [
    {
      name: 'first child',
      children: [
        { name: '4'}, { name: '5'}, { name: '6'}
      ]
    }, {
      name: 'second child'
    }, {
      name: 'third child'
    }
  ]
}
</script>
