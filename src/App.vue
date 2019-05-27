<template>
  <div id="app" class="container">
    <app-new-quote @quoteAdded="newQuoteCome"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuoteHere"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          click in each quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/quoteGrid.vue';
import NewQuote from './components/Newquote.vue';

export default {
 data() {
   return {
     quotes : [
       
     ],
     maxQuote : 10,
   }
 },
 components : {
   appQuoteGrid : QuoteGrid,
   appNewQuote : NewQuote,
 },
 methods: {
   newQuoteCome(quote) {
     this.quotes.push(quote);
   },
   deleteQuoteHere(index) {
     this.quotes.splice(index, 1);
   }
 }
}
</script>

<style>

</style>
