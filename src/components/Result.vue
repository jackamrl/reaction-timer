<script>
export default {
    props: ['score'],
    data() {
        return {

        };
    },
    methods: {

    }
};

</script>

<template>
    <div>
        <p>Reaction time : {{ this.score }} ms</p>
    </div>
</template>

<style  scoped lang="scss">
p {
    text-align: center;
    font-size: 1.2rem;
    color: white;
    margin: 10px auto;
}
</style>
