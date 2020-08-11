<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQoutes="maxQuotes"></app-header>
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
    import Header from './components/Header.vue';
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
            appHeader: Header,
        },
        methods: {
            newQuote(quote) {
                if(this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete some Quotes first!');
                }
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
