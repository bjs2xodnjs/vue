<script setup>
// props 외부에서 들어오는 데이터
    const props = defineProps({
        color: String // 타입 지정
    });

    // color 라는 속성으로 데이터를 받을 수 있다.
    // {{}} template(HTML) 안에서 상수 혹은 변수에 담겨있는 값(Value)를 표시할 때
</script>

<template>
    <!-- :style 이것은 vue문법 
        중괄호 2개 겹쳐져 있는 것은 콧수염(Mustache 표현식)
    -->
    <div :style="{color: props.color}">{{ props.color || 'BLACK!!' }}TIRE</div> 
    <div style="background-color: blue; color: #fff">black Tire</div>
</template>

<style scoped></style>