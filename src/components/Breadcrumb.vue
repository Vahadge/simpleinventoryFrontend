<!-- eslint-disable vue/multi-word-component-names -->
<template>
   <div class="lg:grid grid-flow-row lg:grid-flow-col md-2 mt-2 bg-gray-200 text-black rounded-lg p-4 hidden">
      <div v-for="(item, index) in  JSON.parse( props.breadcrumblinks)" :key="index">
        <div class="flex items-center">
          <svg
            v-if="index != 0"
            class="h-5 w-auto text-gray-400"
            fill="currentColor"
            viewBox="0 0 20 20"
          >
            <path
              fill-rule="evenodd"
              d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
              clip-rule="evenodd"
            ></path>
          </svg>
          <div
            v-if="item.disabled"
            class="ml-2 text-sm font-medium text-gray-500 cursor-default"
          >
            {{ item.name }}
          </div>
          <router-link
            v-else
            :to="item.to"
            class="ml-2 text-lg font-medium text-gray-500 hover:text-gray-700"
          >
            {{ item.name }}
          </router-link>
        </div>
      </div>
    </div>
</template>
<script setup>
    const props = defineProps(["breadcrumblinks"]);
    
    // console.log(props);
</script>