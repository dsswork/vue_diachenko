<template>
    <label>Progress:</label>
    <div class="progress my-progress">    
		<div class="progress-bar" :style="progress"></div>
	</div>
</template>

<script>


export default {
    props: ['width'],
    computed: {
        progress() {
            return 'width:' + this.width + '%'
        }
    },
    setup() {
        
    },
}
</script>

<style scoped>
 .my-progress {
    width: 50%; 
    margin-left: 25%
 }
</style>
