<template>
  <div class="container">
      <appQuoteGrid :quotes="quotes"></appQuoteGrid>
  </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';

    export default {
        data: function(){
          return{
            quotes: ['Just one quote'],
            maxQuotes: 15
          }
        },
        components:{
          'appQuoteGrid': QuoteGrid
        }
      }    
</script>

<style>

</style>
