<template>
  <div >
		子组件
		<input type="text" v-model="nameWatch" >
  </div>
</template>

<script>
export default {

  props: {
    name: {
      type: String,
      required: true,
    },
	},
  name: 'child',
  data () {
    return {
      nameWatch:'',
    }
  },
	mounted(){
    this.nameWatch = this.name
	},
	watch: {
    name(newVal){
      this.nameWatch = this.name
		},
    nameWatch(newVal){
      this.changeVal()
		},
    immediate: false
	},
	methods:{
    changeVal(){
      this.$emit('changeVal', this.nameWatch);
    },
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
