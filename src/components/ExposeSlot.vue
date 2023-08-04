<script setup>
import { ref, defineExpose } from 'vue';
import Button from './Button.vue';

const count = ref(0);

const incrementCount = () => {
  count.value++;
};

defineExpose({ count, incrementCount });
</script>

<template>
    <div style="border: red solid 1px ; padding:12px;">
       
        <p>Count in Child: {{ count }}</p>
        <Button type="danger-button" @click="incrementCount" >incred by Child</Button>
        <hr>
    </div>
</template>
  
