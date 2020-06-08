<template>
    <div>
        <p v-for="(quote, i) in quotesArray" :key="i" @click="deleteQ(i)">{{ quote }}</p>
    </div>
    
</template>

<script>
export default {
    props: {
        quotesArray: Array,
        deleteQuoteFn: Function
    },
    methods: {
        deleteQ(i){
            this.deleteQuoteFn(i)
        }
    }
}
</script>

<style scoped>
    div {
        display: flex;
        flex-wrap: wrap;
    }
    p {
        border: 1px solid black;
        padding: 20px;
        width: 200px;
        font-family: 'Courier New', Courier, monospace;
        margin: 20px;
        cursor: pointer;
    }

    p:hover {
        background-color: lightseagreen;
    }
</style>