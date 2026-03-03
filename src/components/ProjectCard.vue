<template>

	<div class="card col-md-3">
		 <!-- : directive to bind photo to the src attribute -->
	    <img :src="project.image" class="card-img-top card-img" alt="...">
	    <div class="card-body">
	    <h5 class="card-title">{{project.title}}</h5>
	    <p class="card-text">
	       {{project.description}}
	    </p>
	    
	    </div>
	</div>


</template>



<script setup>

	import {defineProps} from "vue";

	defineProps({
		project: Object
	})
	

	// scratch

	// const sample_object = {
	// 	sampleFunction : function(){};
	// 	sampleProperty: value;
	// }

	// sample_object.sampleFunction();

	// const {sampleFunction} = sample_object;

	// sampleFunction();

</script>


