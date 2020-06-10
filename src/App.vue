<template>
    <div class="container">
        <appBar :quoteCount="quoteCount" :maxQuotes="maxQuotes"></appBar>
        <app-input :addQuoteFn="addQuote"></app-input>
        <app-card :quotesArray="quotes" v-if="quotes.length > 0" :deleteQuoteFn="deleteQuote"></app-card>
        <app-footer></app-footer>
        <hr>
        <hr>
        <hr>
        <hr>
        <hr>
        <button @click="printSvg">print file</button>
    </div>
</template>

<script>
    import Bar from "./components/quotesBar.vue";
    import Input from "./components/quoteInput.vue";
    import Card from "./components/quoteCard.vue";
    import Footer from "./components/quotesFooter.vue";
    import axios from 'axios'

    export default {
        data: function(){
            return {
                quotes: [],
                maxQuotes: 10,
                quoteCount: 0
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
                if(this.quotes.length >= this.maxQuotes){
                    return alert("please delete a quote")
                }
                this.quotes.push(q)
                this.quoteCount++
            },
            deleteQuote(i){
                this.quotes.splice(i,1)
                this.quoteCount--
            },
            printSvg(){
                axios.post("localhost:1337/svgToPdf")
                .then(res => {
                    console.log(res)
                })
            }
        }
    }
</script>

<style>
    
</style>
