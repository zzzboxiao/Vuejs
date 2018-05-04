!#=============== VueJS 组件制作 ==================

	<input v-model="searchText">
    等价于：
    <input v-bind:value="searchText" v-on:input="searchText = $event.target.value">
    总结:给组件添加 v-model 属性时，默认会把 value 作为组件的属性，然后把 'input' 值作为给组件绑定事件时的事件名
    因此,使用v-model监听blur事件,但必须触发($emit) input事件,若想操作input触发onblur的同时,而不是oninput事件
	<input :type="inputType" @blur="$emit('input', $event.target.value)" class="input-box-el">

    v-model已包含value属性,所以不需要在子组件中暴露value属性  
	


quiInput.vue  
    
    input输入框组件,子模板


useInput.vue  

    使用input输入框组件的父模板
