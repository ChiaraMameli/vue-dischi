<template>
    <main>
        <div class="container">
            <div v-if="isLoading" class="loading-message">Loading..</div>
            <div v-else class="box">
                <DiscCard :disc="disc" v-for="(disc, i) in filteredDiscs" :key="i"/>
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
    props:{
        selectedGenre: String,
    },
    computed:{
        filteredDiscs(){
            if(!this.selectedGenre) return this.discs;
            return this.discs.filter((disc) => disc.genre === this.selectedGenre)
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.discs = res.data.response;
            this.isLoading = false;

            const genres = [];
            this.discs.forEach((disc) => {
                if(!genres.includes(disc.genre)) genres.push(disc.genre);
            });
            this.$emit('fetched-genres', genres)

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
            justify-content: center;
            padding: 50px 0;
        }
        
        .loading-message {
            font-size: 3rem;
            color: #FFF;
            text-align: center;
        }
    }
</style>