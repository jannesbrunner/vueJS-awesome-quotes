<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" v-bind:key="quote" @click.native="deleteQuote(index)">
            <p>{{ quote }}</p>
        </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
    props: ['quotes'],
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index) {
            console.log(index);
            this.$emit('quoteDelete', index);
        }
    }
}
</script>

<style scoped>

</style>