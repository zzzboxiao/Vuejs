<!--
    <input v-model="searchText">
    等价于：
    <input v-bind:value="searchText" v-on:input="searchText = $event.target.value">
    总结:给组件添加 v-model 属性时，默认会把 value 作为组件的属性，然后把 'input' 值作为给组件绑定事件时的事件名
    因此,要使用v-model,监听blur事件,但必须触发($emit) input事件,此时操作input会触发onblur,而不是oninput事件
    使用v-model包含value属性
-->
<template>
  <div class="input-box">
    <div class="input-box-add">
      <span class="input-box-name">{{inputName}}</span>
      <input :type="inputType" @blur="$emit('input', $event.target.value)" class="input-box-el">
    </div>
    <!-- <input :type="inputType" :value="value" @blur="$emit('input', $event.target.value)"> -->
    <span class="input-box-msg">{{msg}}</span>
  </div>
</template>
<script>
export default {
  name: 'form-input',
  props: ['inputType','inputName','msg'],
}
</script>
<style scoped>
  .input-box{
    width: 400px;
    height: 100px;
  }
  .input-box-add{
    width: 100%;
    height: 40px;
  }
  .input-box-name{
    font-size: 20px;
    padding-right: 10px;
  }
  .input-box-el{
    width: 300px;
    height: 36px;
    padding-left: 8px;
    border: solid 2px #d2d2d2;
    border-radius: 5px;
  }
  .input-box-el:hover{
    border: solid 2px #2785a7;
  }
  .input-box-msg{
    font-size: 12px;
    color: red;
    margin-left: 75px;
  }
</style>
