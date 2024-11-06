<script>

export default{

    props: {
        currencies: {
            type: Array,
        }
    },

    data(){

        return{
            
        }
    },

    methods: {
        
    }
}

</script>

<template>

    <div>

        <input 
        type= "number"
        v-model.trim= "amount"
        @input=""
        placeholder="0,00"
        >

        <p>{{ amount }}</p>

        <select 
        name="" 
        id=""
        v-model="selectedCurrency"
        >
            <option :value="currency" v-for="currency in currencies">{{ currency }}</option>
        </select>

    </div>

</template>

<style scoped lang="scss">

</style>
