<template>
  <div class="row">
      <app-quote v-for="(eachQuote, index) in quotes" :key="eachQuote" @click.native="deleteQuote(index)">
          {{  eachQuote }}
      </app-quote>
  </div>
</template>

<script>
import Quote from './quote.vue';

export default {
    props: ['quotes'],
    data() {
        return {
            
        }
    },
    components: {
        appQuote : Quote,
    },
    methods: {
        // i need index to know which quote should delete, so modify v-for(eachQuote, index)
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style>

</style>
