<template>
	<div>
		父组件
		<input type="text" v-model="name"><br/>
		<child :name="name" @changeVal="childVal"></child>
	</div>
</template>

<script>
  import Child from './child'

  export default {
    components: {Child},
    name: 'father',
    data() {
      return {
        name: 'father msg'
      }
    },
		methods:{
      childVal(data){
        this.name=data
			}
		}
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
