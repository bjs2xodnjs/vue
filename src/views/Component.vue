<script setup>
import FrontWheel from '@/components/FrontWheel.vue';
import RealWheel from '@/components/RearWheel.vue';
import { useCounterStore } from '@/stores/counter.js';
const counterStore = useCounterStore();
</script>

<template>
    <h1>Hello Vue!</h1>
    <h1>Hello Vue!</h1>
    <button @click="counterStore.increment">회전</button>
    <!-- <h1>Hello Vue!</h1>
<FrontWheel></FrontWheel>
<RealWheel></RealWheel> -->


<div class="car">
<FrontWheel/><FrontWheel />
</div>
<div class="car">
<RealWheel/><RealWheel />
</div>
</template>


<style scoped>
.car {
display: flex;
gap: 10px;
}

</style>