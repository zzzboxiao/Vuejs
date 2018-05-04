<template>
  <div class="input-box">
    <div class="input-box-add">
      <span class="input-box-name">{{inputName}}</span>
      <input :type="inputType" @blur="$emit('input', $event.target.value)" class="input-box-el">
    </div>
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
    position: relative;    
  }
  .input-box-add{
    width: 500px;
    height: 30px;
    position: relative;
    display: flex;
    align-items: center;
    -webkit-align-items:center;
  }
  .input-box-name{
    position: absolute;
    font-size: 16px;
    top:3px;
    right: 370px;
    /* padding-left: 34px; */
  }
  .input-box-el{
    position: absolute;
    width: 60%;
    height: 30px;
    margin-left: 20px;
    top: 0;
    right: 50px;
    padding-left: 7px;    
    border: solid 1px #d2d2d2;
    border-radius: 3px;
  }
  .input-box-el:hover{
    border: solid 2px #2785a7;
  }
  .input-box-msg{
    position: absolute;
    font-size: 12px;
    color: red;
    top: 32px;
    left: 150px;
    /* margin-left: 150px; */
  }
</style>
