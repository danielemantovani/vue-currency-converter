<script>

import CurrencyInput from './components/CurrencyInput.vue';

export default{

    components:{
        CurrencyInput,
    },

    data(){

        return{
            currencies: ['EUR', 'USD']
        }
    }
}

</script>

<template>

    <div>
        <CurrencyInput :currencies= "currencies" />
    </div>
    
</template>

<style lang="scss">

    div{
        text-align: center;
    }

</style>
