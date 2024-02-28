<template>
  <div class="flex flex-col border p-4 rounded min-w-[200px]">
    <div class="bg-blue-600 text-white flex justify-between">
      <span>{{  item.name }}</span>
      <button v-if="item.children?.length ?? 0 > 0" class="bg-white text-black text-xs" @click="collapsed = !collapsed">Collapse</button>
    </div>
    <div class="bg-red-800 flex flex-wrap" v-if="!collapsed">
      <v-card v-for="(child, i) in item?.children ?? []" :key="i" :item="child"/>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import VCard from '@/components/VCard.vue'
import type { IEntity } from '@/types'
defineProps<{ item: IEntity }>()

const collapsed = ref(false)
</script>