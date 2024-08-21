<template>
    <div class="body">
      <div class="container">
        <RunBoo></RunBoo>
        <TeamIntro></TeamIntro>
        <HistoryFoot></HistoryFoot>
        <TeamHeart></TeamHeart>
        <ThisPractice></ThisPractice>
      </div>
    </div>
</template>

<script>

import RunBoo from '../components/RunBoo.vue'
import TeamIntro from '../components/TeamIntro.vue'
import HistoryFoot from '../components/HistroyFoot.vue'
import TeamHeart from '../components/TeamHeart.vue';
import ThisPractice from '@/components/ThisPractice.vue';

export default {
    components:{
        RunBoo,TeamIntro,HistoryFoot,TeamHeart,ThisPractice
    }
}

</script>

<style scoped> 
* {
    margin: 0px;
    padding: 0px;
}
.body {
    line-height: 1.6;
    background-color: #f4f4f4;
}
.container {
    width: 80%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 5px 5px;
    background-color: white
}
</style>