<template>
  <div>
    <Progess width='50'/>
    <MyInput v-for="item in info" :key="item.name" :name="item.name" :isRight="0"/>
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
  } 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.my-button {
	margin: 30px;
}
</style>
