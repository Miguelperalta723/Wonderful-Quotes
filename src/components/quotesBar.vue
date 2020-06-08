<template>
    <div class="bar">
        <div class="inside-bar" :style="{width: (quoteCount/maxQuotes) * 100 + '%'}" v-if="quoteCount > 0">
            {{ quoteCount }} / {{ maxQuotes }}
        </div>
    </div>
</template>

<script>
export default {
    props: {
        quoteCount: Number,
        maxQuotes: Number
    }
}
</script>

<style scoped>
    .bar {
        margin-top: 20px;
        border: 1px solid black;
        text-align: center;
        height: 20px;
    }

    .inside-bar {
        background-color: lightblue;
        text-align: center;
        height: 100%;
    }
</style>