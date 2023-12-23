<template>
	<div id="app">
	  <dynamic-layout :layout="layout" @itemClick="showComponentList"></dynamic-layout>
	  <component-list v-if="selectedItem" @selectComponent="selectComponent"></component-list>
	</div>
  </template>

  <script>
  import DynamicLayout from "@/components/DynamicLayout.vue";
  import ComponentList from "@/components/ComponentList.vue";

  export default {
	data() {
	  return {
		layout: [
		  [null, null, null],
		  [null, null, null],
		  [null, null, null],
		],
		selectedItem: null,
	  };
	},
	components: {
	  DynamicLayout,
	  ComponentList,
	},
	methods: {
	  showComponentList(item) {
		this.selectedItem = item;
	  },
	  selectComponent(component) {
		this.layout[this.selectedItem.row][this.selectedItem.col] = component;
		this.selectedItem = null;
	  },
	},
  };
  </script>

  <style>
  /* Add your global styles here */
  </style>