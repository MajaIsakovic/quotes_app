<template>
  <div class="container">
      <appQuoteHeader :quoteQount="quotes.length" :maxQuotes="maxQuotes"></appQuoteHeader>
      <!-- listening to event from new quote component -->
      <!-- also: @quoteAdded="newQuote($event)" -->
      <!-- but we dont have to put nothing as the parametar Vue wil do it behind the scenes -->
      <appNewQuote @quoteAdded="newQuote"></appNewQuote>
      <appQuoteGrid :quotes="quotes" @quoteDeleted="quoteDelete"></appQuoteGrid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Info: Click on a quote to delete it!
          </div>
        </div>
      </div>
  </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';
    import NewQuote from './components/NewQuote';
    import QuoteHeader from './components/QuoteHeader';
  
    export default {
        data: function(){
          return {
            quotes: ['Just one quote'],
            maxQuotes: 10
          }
        },
        components:{
          'appQuoteGrid': QuoteGrid,
          'appNewQuote': NewQuote,
          'appQuoteHeader': QuoteHeader
        },
        methods:{
          newQuote(quote){
            if(this.quotes.length >= this.maxQuotes){
              alert('Please delete quotes first!');
            } else {
              this.quotes.push(quote);
            }
          },
          quoteDelete(index){
              this.quotes.splice(index, 1);
          }
        }
      }    
</script>

<style>

</style>
