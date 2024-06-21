<template>
    <h1>You reacted in {{ score }}ms</h1>
    <h5>Rank: {{ rank }}</h5>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        };
    },
    mounted() {
        if (this.score < 250) {
            this.rank = 'ninja fingers';
        } else if (this.score < 400) {
            this.rank = 'rapid';
        } else {
            this.rank = 'snail pace';
        }
    },
};
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
}

button {
    background: #0faf87;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
}
button[disabled] {
    opacity: 0.2;
    cursor: not-allowed;
}
</style>
