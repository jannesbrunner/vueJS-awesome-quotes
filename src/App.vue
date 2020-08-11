<template>
    <div class="container">
        <app-quote-grid :quotes="quotes" @quoteDelete="deleteQuote"></app-quote-grid>
        <app-new-quote @quoteNew="newQuote"></app-new-quote>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Just click on a Quote to delete it
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    export default {
        data: function() {
            return {
                quotes: [
                    'Just a example Quote to see something'
                ],
                maxQuotes: 10,
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
        },
        methods: {
            newQuote(quote) {
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>
