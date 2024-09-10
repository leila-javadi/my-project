<template>
	<p>{{ message }}</p>
	<button :disabled="isButtonDisabled ? true : false">Button</button>
	<p v-if="seen" @click="() => showLogs(message)">Now you see me</p>
	<p >{{isButtonDisabled ? 'Yes' : 'No'}}</p>
	<p >{{isButtonDisabled ? 'Yes' : 'No'}}</p>
	<input type="text" v-model="message" >
	<li v-for="item,index in items" :key="index">
		{{ item.message }}
	</li>
</template>

<script>

export default {
  name: 'App',
  data() {
        return {
			message: null,
			isButtonDisabled:true,
			seen: true,
			items: [{ message: 'Foo' }, { message: 'Bar' }]
		};
    },
  components: {

  },
  mounted(){
	console.log("yhhhhh")
  },
  methods:{
	showLogs(name){
		console.log(name)
	},

  },
  watch:{
	message(){
		let self =this;
		if(this.isButtonDisabled){
			console.log(self.message)
		}
	}
  }
}
</script>

<style>

</style>
