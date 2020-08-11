<template>
   <div class="row">
       <div class="cols-sm8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
           <label>Quote<label>
            <textarea class="form-control" rows="3" v-model="quote"></textarea>
       </div>
       <div class="cols-sm8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
           <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
       </div>
   </div>
</template>

<script>
export default {
    data: function() {
        return {
            quote: ''
        };
    },
    methods: {
        createNew() {
            this.$emit('quoteNew', this.quote);
            this.quote = '';
        }
    }
}
</script>

<style scoped>
    
</style>