<template>
	<div class="dynamic-layout">
	  <div v-for="(row, rowIndex) in layout" :key="rowIndex" class="row">
		<div v-for="(col, colIndex) in row" :key="colIndex" @click="itemClick(rowIndex, colIndex)">
		  <component :is="col" v-if="col"></component>
		</div>
	  </div>
	</div>
  </template>

  <script>
  export default {
	props: {
	  layout: Array,
	},
	methods: {
	  itemClick(row, col) {
		this.$emit("itemClick", { row, col });
	  },
	},
  };
  </script>

  <style scoped>
  /* Add your component-specific styles here */
  </style>