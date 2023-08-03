<script setup>

const props  = defineProps({
    type:{
        type:String,
        default:"primary-button"  // primary-button secondary-button  , danger-button
    }
})

</script>
<template>
    <button :class="`${props.type}`">
        <slot ></slot>
    </button>
</template>


<style scoped>
 .button-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

button {
  padding: 12px 24px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: background-color 0.3s ease;
  margin: 5px;
}

.primary-button {
  background-color: #007bff;
  color: #fff;
}

.secondary-button {
  background-color: #6c757d;
  color: #fff;
}

.danger-button {
  background-color: #dc3545;
  color: #fff;
}

button:hover {
  background-color: #555;
}
</style>