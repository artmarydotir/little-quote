<template>
  <div id="app" class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuoteCome"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuoteHere"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-warning">
          click in each quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/quoteGrid.vue';
import NewQuote from './components/Newquote.vue';
import Header from './components/Header.vue';

export default {
 data() {
   return {
     quotes : [
       'Just a defualt quote!'
     ],
     maxQuotes : 10,
   }
 },
 components : {
   appQuoteGrid : QuoteGrid,
   appNewQuote : NewQuote,
   appHeader : Header,
 },
 methods: {
   newQuoteCome(quote) {
     if(this.quotes.length >= this.maxQuotes) {
       return alert('please remove one quote, to add another')
     }
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
