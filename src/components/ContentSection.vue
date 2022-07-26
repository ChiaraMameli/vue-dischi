<template>
<main>
    <div class="container">
        <div v-if="isLoading" class="loading-message">Loading..</div>
        <div v-else class="box">
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
            discs: [],
            isLoading: true,
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.discs = res.data.response;
            this.isLoading = false;
        }).catch(() => {
            alert('Impossibile caricare la pagina');
        }).then(() => {
            this.isLoading = false;
        })
        
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';
    main{
        background-color: $dark_blue;
        min-height: calc(100vh - 60px);

        .box{
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            padding: 50px 0;
        }

        .loading-message {
            font-size: 3rem;
            color: #FFF;
            text-align: center;
        }
    }
</style>