<script>

import axios from 'axios';
import CurrencyInput from './components/CurrencyInput.vue';

export default{

    components:{
        CurrencyInput,
    },

    data(){

        return{
            currencies: [],
        }

    },

    mounted(){
        axios.get('https://api.frankfurter.app/currencies')
        .then(resp => {
            this.currencies = Object.keys(resp.data);
        })

        .catch(error =>{
            console.log('Errore nel recupero delle valute', error)
        })
    },

    methods: {

        // Utilizzando la tecnica del destructuring (parentesi graffe nella dichiarazione dei parametri della funzione) rendo più chiaro e leggibile il codice e semplifico l'accesso ai valori
        listenAmountUpdate({ amount, currency }) {
        console.log("Valore aggiornato:", amount, "Valuta selezionata:", currency);
        },

    }
}

</script>

<template>

    <div>
        <CurrencyInput :currencies= "currencies" @update-amount ="listenAmountUpdate" />
    </div>
    
</template>

<style lang="scss">

    div{
        text-align: center;
    }

</style>
