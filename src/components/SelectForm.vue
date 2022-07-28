<template>
    <div>
        <select name="genres" id="genres" v-model="selectedOption" @change="emitChange">
        <option value="">Choose a option</option>
        <option v-for="option in options" :key="option" :value="option" >{{option}}</option>
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
    },
    methods:{
        emitChange(){
            this.$emit('change-option', this.selectedOption);
        }
    }
}
</script>

<style>

</style>
