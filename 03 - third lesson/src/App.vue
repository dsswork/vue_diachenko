<template>
  <div>
    <Progess :width="progress"/>
    <MyInput v-for="(item, i) in info" :key="item.name" :name="item.name" :id="i" :value="item.value" :isRight="item.isValidate" @inputData="updateData"/>
	<button class="btn btn-primary my-button" disabled>
		Send Data
	</button>
  </div>
</template>

<script>

import Progess from '@/components/Progress'
import MyInput from '@/components/MyInput'
export default {
  name: 'App',
  components: {
    Progess,
    MyInput
  },
  data: function () {
    return {
      info: [
					{
						name: 'Name',
						value: '',
						pattern: /^[a-zA-Z ]{2,30}$/
					},
					{
						name: 'Phone',
						value: '',
						pattern: /^[0-9]{7,14}$/
					},
					{
						name: 'Email',
						value: '',
						pattern: /.+/
					},
					{
						name: 'Some Field 1',
						value: '',
						pattern: /.+/
					},
					{
						name: 'Some Field 2',
						value: '',
						pattern: /.+/
					}
				]
    }
  },
  methods: {
	updateData(value, id) {
		this.info[id].value = value
		this.checkValid(id)
	},
	checkValid(id) {
		let item = this.info[id]
		if(item.value) {
			item.isValidate = 2
			if(item.pattern.test(this.info[id].value)) {
				item.isValidate = 1
			}
		} else {
			item.isValidate = 2
		}
	}
},
  computed: {
		progress() {
			let how = this.info.reduce(function(accumulator, currentValue) {
			if(currentValue.isValidate===1)
				accumulator++;
				return accumulator;
				}, 0)					
			return 'width:' + how/this.info.length*100 + '%';
		}
  },
  created() {
		this.info.forEach(element => {
		element.isValidate = 0;
		});
	}, 
}
</script>

<style>


.my-button {
	margin: 30px;
}
</style>
