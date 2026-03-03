<template>
	<section class="pb-5" id="projects">
	    <h1 class="mt-5 mb-5 pb-4 text-center">My Projects</h1>
	    <div 
	    	v-for="(group, index) in chunkedProjects"
	    	:key="index"
	    	class="card-deck my-5 justify-content-center"
	    >
	    	<ProjectCard 
	    		v-for="project in group"
	    		:key="project.id"
	    		:project="project"
	    	/>
	    	
	    </div>


	</section>
</template>

<script setup>
	
	import {computed} from "vue";
	import ProjectCard from "./ProjectCard.vue";
	import projects from "../data/projects.json";

	const chunkSize = 3;

	const chunkedProjects = computed(() => {

		const chunks = [];
		// chuncks = [ [ {0},{1},{2}], [{3}, {4}, {5}], [{6},{7},{8}]]


		for(let i = 0; i < projects.length; i+=chunkSize){
			// i = 0
			//               0, 3 [meaning: index 0, 1, 2]

			// i = 3
			//				(3, 6) meaning push item in index 3, 4, 5

			// i = 6
			//           	(6, 9) meaning push item in index 6, 7, 8
			chunks.push(projects.slice(i, i+chunkSize));
		}

		return chunks;
	})
</script>