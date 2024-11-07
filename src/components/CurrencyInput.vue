<script>

export default{

    props: {
        currencies: {
            type: Array,
        }
    },

    data(){

        return{
            selectedCurrency: 'EUR',
        }
    },

    methods: {
        emitAmount(){
            this.$emit("update-amount", { 
                amount: this.amount, 
                currency: this.selectedCurrency 
            });
        }
    },
        
}


</script>

<template>

    <div>

        <p>{{ amount }} {{ selectedCurrency }}</p>

        <input 
        type= "number"
        v-model.trim= "amount"
        @input="emitAmount"
        placeholder="0,00"
        >

        <select 
        name="" 
        @change="emitAmount"
        v-model="selectedCurrency"
        >

            <option :value="currency" v-for="currency in currencies">{{ currency }}</option>

        </select>

    </div>

</template>

<style scoped lang="scss">

</style>
