<template>
    <div class="form-group my-input">
		<label>{{ this.name }}</label>
		<input type="text" class="form-control" :class="isError">
	</div>
</template>

<script>


export default {
    props: ['name', 'isRight'],
    computed: {
        isError() {
            switch (this.isRight) {
                case 0: return ''
                case 1: return 'input-green'
                case 2: return 'input-red'
            }
            return ''
        }
    },
    setup() {
        
    },
}
</script>

<style scoped>
 .my-input {
    width: 50%; 
    margin-left: 25%;
    margin-top: 10px;
 }

 .input-red {
     border-color: red;
 }

 .input-green {
     border-color: green;
 }

</style>
