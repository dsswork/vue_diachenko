<template>
    <label>Progress:</label>
    <div class="progress my-progress">    
		<div class="progress-bar" :style="width"></div>
	</div>
</template>

<script>


export default {
    props: ['width'],
}
</script>

<style scoped>
 .my-progress {
    width: 50%; 
    margin-left: 25%
 }
</style>
