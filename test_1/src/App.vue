<template>
	<div id="app">
	  <session
		v-for="(session, index) in sessions"
		:key="index"
		:session="session"
		@updateSession="updateSession(index)"
	  ></session>
	</div>
  </template>

  <script>
  import Session from "@/components/Session.vue";

  export default {
	data() {
	  return {
		sessions: [
		  { id: 1, position: { x: 0, y: 0 }, color: "red", fontSize: "16px", fontFamily: "Arial", visible: true },
		  { id: 2, position: { x: 0, y: 0 }, color: "blue", fontSize: "18px", fontFamily: "Verdana", visible: true },
		  // Add more sessions as needed
		],
	  };
	},
	components: {
	  Session,
	},
	methods: {
	  updateSession(index) {
		// Update CMS data or perform other actions when a session is updated
	  },
	},
  };
  </script>

  <style>
  /* Add your global styles here */
  </style>
