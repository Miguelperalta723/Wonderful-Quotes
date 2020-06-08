<template>
    <div>
        <div class="inside-bar">
            {{ quoteCount }}/10
        </div>
    </div>
</template>

<script>
export default {
    data: function(){
        return {
            quoteCount: 0,
            maxQuotes: 10
        }
    }
}
</script>

<style scoped>
    div {
        border: 1px solid black;
        text-align: center;
    }

    .inside-bar {
        background-color: lightblue;
    }
</style>