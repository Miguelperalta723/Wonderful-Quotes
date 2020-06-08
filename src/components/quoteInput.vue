<template>
    <div>
        <h4>Quote</h4>
        <input type="text" @input="updateQuote">
        <button @click="addQuoteFn(quoteToAdd)">add Quote</button>
    </div>
    
</template>

<script>
export default {
    data: function(){
        return {
            quoteToAdd: ""
        }
    },
    props: {
        addQuoteFn: Function
    },
    methods: {
        updateQuote(e){
            this.quoteToAdd = e.target.value
        }
    }
}
</script>

<style scoped>
    div {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    input {
        height: 50px;
        width: 400px;
    }
</style>