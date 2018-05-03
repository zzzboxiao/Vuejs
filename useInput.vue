<template>
  <div class="content">
    <h3>input组件demo</h3>
    <form-input :inputType="'type'" :inputName="'用户名'" v-model="username" v-on:input="dosth" :msg="remind"></form-input>
  </div>
</template>
<script>
import formInput from './quiInput.vue'
export default {
  name: 'inputVue',
  data() {
    return {
      username: '',
      remind:''
    }
  },
  components: {
      'form-input':formInput
  },
  methods:{
      dosth:function(val){
        console.log('val: ',val);
        console.log('username: ',this.username);
        if(val.length==0){
            this.remind = '请输入用户名'
        }else{
            this.remind = ''
        }
      }
  },
  watch:{ //监听username属性
      username:function(val){
          console.log('watch username',val)
      }
  },
}
</script>
<style scoped>
  .content{
    display: flex;
    display: -webkit-flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 800px;
    height: 400px;
    margin: 0 auto;
    background:#fafafa;
    /* border:solid 1px red; */
  }
  h3{
    position: absolute;
    top: 20px;
  }
</style>