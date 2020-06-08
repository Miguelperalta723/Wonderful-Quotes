<template>
    <div class="container">
        <appBar></appBar>
        <app-input :addQuoteFn="addQuote"></app-input>
        <app-card :quotesArray="quotes" v-if="quotes.length > 0" :deleteQuoteFn="deleteQuote"></app-card>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Bar from "./components/quotesBar.vue";
    import Input from "./components/quoteInput.vue";
    import Card from "./components/quoteCard.vue";
    import Footer from "./components/quotesFooter.vue";

    export default {
        data: function(){
            return {
                quotes: []
            }
        },
        components: {
            appBar: Bar,
            appInput: Input,
            appCard: Card,
            appFooter: Footer
        },
        methods: {
            addQuote(q){
                this.quotes.push(q)
            },
            deleteQuote(q){
                this.quotes.pop(q)
            }
        }
    }
</script>

<style>
    
</style>
