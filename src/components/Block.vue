<template>
    <div v-if="showBlock" class="block" @click="stopTimer">
        CLICK ME !
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            }, 1);
        },

        stopTimer() {
            clearInterval(this.timer);
            this.$emit('end', this.reactionTime);
        },


    }
}
</script>

<style lang="scss" scoped>
.block {
    width: 400px;
    background-color: rgb(23 51 37);
    border-radius: 10px;
    margin: 40px auto;
    font-weight: bolder;
    text-align: center;
    line-height: 100px;
    font-size: 1.4rem;
    color: white;
    padding: 100px 0;
    cursor: pointer;
}
</style>