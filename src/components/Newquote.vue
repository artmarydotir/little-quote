<template>
  <div class="row">
    <form class="col-md-12">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-10 col-md-offset-1 form-group">
        <label for="">Quote:</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
    </div>
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <button class="btn btn-primary" @click.prevent="createNew">
        Add Quote
      </button>
    </div>
    </form>
  </div>
</template>

<script>

export default {
    data() { 
        return {
            quote : '',
        }
    },
    methods: {
      createNew() {
        if(this.quote === '') {
          alert("quote cant be empty!");
          return;
        }
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    }
}
</script>

<style>
.panel-body {
  font-family: cursive;
  font-size: 24px;
  columns: #444;
  border: 1px solid rgb(68, 67, 67);
  padding: 12px; 
  margin: 16px auto;
}
</style>
