<template>
    <div class="container">
        <app-quote-grid :quotes="quotes"></app-quote-grid>
        <app-new-quote @quoteNew="newQuote"></app-new-quote>
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
            }
        }
    }
</script>

<style>
</style>
