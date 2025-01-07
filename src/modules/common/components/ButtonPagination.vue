<template>
  <div class="flex justify-center space-x-3 py-10 bg-gray-100">
    <button
      :disabled="page === 1"
      @click="$router.push({ query: { page: page - 1 } })"
      class="hover:bg-blue-600 transition-all flex items-center px-4 py-1.5 text-white rounded-lg  space-x-1.5 bg-blue-500 disabled:bg-gray-300"
    >
      <ArrowLeftIcon />
      <span>Anteriores</span>
    </button>

    <button
      :disabled="hasMoreData"
      @click="$router.push({ query: { page: page + 1 } })"
      class="hover:bg-blue-600 transition-all flex items-center px-4 py-1.5 text-white rounded-lg  space-x-1.5 bg-blue-500 disabled:bg-gray-300"
    >
      <span>Siguientes</span>
      <ArrowRightIcon />
    </button>

  </div>
</template>

<script setup lang="ts">
import ArrowLeftIcon from '@/icons/ArrowLeftIcon.vue';
import ArrowRightIcon from '@/icons/ArrowRightIcon.vue';

interface Props {
  page: number;
  hasMoreData: boolean;
}

defineProps<Props>()

</script>
