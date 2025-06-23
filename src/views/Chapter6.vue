<script setup>
import { reactive, computed } from 'vue';

const state = reactive ({
    mvpId: 9,
    players: [
        { id: 7, name: 'john Doe'},
        { id: 9, name: 'Jane Lee'},
        { id: 12, name: 'James ark'},
    ]
})

const getMvpName = () => {
    if (state.mvpId) {
        const player = state.players.find((item) => item.id === state.mvpId);

        if(player) {
            return player.name;
        }
    }
    return "없음";
};

const getMvpNameNice = () => {
    console.log('getMvpNameNice 메소드!')
    return state.players.find(item => item.id === state.mvpId)?.name || '없음'  
}

// 컴퓨티드
const computedMvpName = computed(() => {
    console.log('getMvpNameNice 컴퓨티드!')
    return state.players.find(item => item.id === state.mvpId)?.name || '없음'  
});

</script>


<template>
    <h1>Chapter6.vue</h1>
    <h1>오늘의 MVP</h1>
    <template v-if="state.mvpId">
        <!-- Optional Chainind -->
        {{ state.players.find(item => item.id === state.mvpId)?.name || '없음' }}
    </template>

    <div>{{ getMvpName() }}</div>
    <div>nice: {{ getMvpName() }}</div>
    <div>nice: {{ getMvpName() }}</div>
    <div>nice: {{ getMvpName() }}</div>
    <div>{{ 'Jane Lee' }}</div>
    <div>computed: {{ computedMvpName }}</div>
    <div>computed: {{ computedtMvpName }}</div>
    <div>computed: {{ computedtMvpName }}</div>
</template>

<style scoped>

</style>