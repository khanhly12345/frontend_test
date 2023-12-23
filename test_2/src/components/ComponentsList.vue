<template>
	<div class="component-list">
	  <div v-for="component in components" :key="component.name" @click="selectComponent(component)">
		{{ component.name }}
	  </div>
	</div>
  </template>

  <script>
  export default {
	data() {
	  return {
		components: [
		  { name: "ComponentA" },
		  { name: "ComponentB" },
		  // Add more components as needed
		],
	  };
	},
	methods: {
	  selectComponent(component) {
		this.$emit("selectComponent", component.name);
	  },
	},
  };
  </script>