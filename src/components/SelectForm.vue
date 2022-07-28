<template>
    <div>
        <select name="genres" id="genres" v-model="selectedOption">
        <option value="">{{`Choose a ${option}`}}</option>
        <option :value="option" v-for="option in options" :key="option"></option>
        </select>
    </div>    
</template>

<script>

export default {
    name: 'SelectForm',
    data(){
        return{
            selectedOption: '',
        }
    },
    props:{
        options: Array,
    }
}
</script>

<style>

</style>
