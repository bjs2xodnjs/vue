<script setup>
import { ref, reactive, nextTick } from 'vue';

const pushUp = ref(0); //ref 메소드는 반응형 상태 객체 주소걊을 리턴, 초기값을 value 속성에 저장
const state = reactive({
    sitUp: 0 // 윗몸 일으키기 개수
})
const increasePushUp = () => {
    pushUp.value++; // 	Ref 객체 내부 값(value)을 변경 — 가능함
    nextTick(() => {
    console.log(document.querySelector('#pushUp').innerText);
    console.log('푸시업 이벤트 발생!, pushUp.value')
})
};

const increasePushUp2 = () => {
    state.sitUp++;
    console.log ('싯업 이벤트 발생!, state.sliup')
}
</script>


<template>
    <h1>chapter5.vue - 반응형 상태</h1>
    <hr>
    <div id="pushUp">팔 굽혀 펴기 : {{ pushUp }}</div>
    <div id="silUp">윗몸 일으키기 : {{ state.sitUp }}</div>
    <hr>
    <button @click="increasePushUp">팔 굽혀 펴기 증가</button>
    <button @click="increasePushUp2">윗몸 일으키기 증가</button>
</template>

<style scoped>

</style>