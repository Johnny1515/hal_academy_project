<script setup>
import { reactive } from 'vue';
import Button from './Button.vue';


const emits = defineEmits(["onSuccess"])
const state = reactive({
    form:{
        title:""
    },
    id:0
})
function onSubmitSuccess(e){
    // console.log("YES",e)
    // e.defaultPrevented = true
    if(state.form.title.length > 0){
        emits("onSuccess", {
            id: state.id,
            title:state.form.title
        })
        state.id++
        state.form.title = ""
    }
}
</script>
<template>
    <div class="form-container">
        <h2>Form Product</h2>

        <form  >
        <label for="title">Title Product:</label>
        <input @keypress.enter="onSubmitSuccess" v-model="state.form.title" type="text" id="title" name="title" placeholder="Enter your title" required>
        
        </form>
        <Button @click="onSubmitSuccess" >
            New Product
        </Button>
    </div>
</template>


<style scoped>
 .form-container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
}

form {
  display: flex;
  flex-direction: column;
}

label {
  font-weight: bold;
  margin-bottom: 5px;
}

input,
textarea {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-bottom: 10px;
}

textarea {
  resize: vertical;
}

input[type="submit"] {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

input[type="submit"]:hover {
  background-color: #0056b3;
}
</style>