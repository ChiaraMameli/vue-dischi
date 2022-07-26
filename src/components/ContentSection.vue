<template>
<main>
    <div class="container">
        <div class="box">
            <DiscCard :disc="disc" v-for="(disc, i) in discs" :key="i"/>
        </div>
    </div>
</main>
</template>

<script>
import DiscCard from './DiscCard.vue';
import axios from 'axios';

export default {
    name: "ContentSection",
    components: { 
        DiscCard,
        },
    data(){
        return {
            discs: []
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.discs = res.data.response;
            console.log(this.discs)

        })
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';
    main{
        background-color: $dark_blue;

        .box{
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            padding: 50px 0;
        }
    }
</style>