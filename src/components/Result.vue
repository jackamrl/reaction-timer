<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        };
    },

    mounted() {
        if (this.score < 400) {
            this.rank = 'Godlike 😊';
        } else if (this.score < 500) {
            this.rank = 'Pro 🙌';
        } else if (this.score < 600) {
            this.rank = 'Average 👍';
        } else {
            this.rank = 'Snail 🐌';
        }
    },
    methods: {

    }
};

</script>

<template>
    <div>
        <p>Reaction time : {{ this.score }} ms</p>
        <p class="rank"> {{ rank }}</p>
    </div>
</template>

<style  scoped lang="scss">
p {
    text-align: center;
    font-size: 1.2rem;
    color: white;
    margin: 10px auto;
}

.rank {
    font-size: 1.5rem;
    font-weight: bold;
    color: aquamarine;
}
</style>
