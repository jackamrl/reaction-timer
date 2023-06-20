<template>
    <div v-if="showBlock" class="block">
        click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
        }, this.delay);
    },
}
</script>

<style lang="scss" scoped>
.block {
    width: 400px;
    background-color: rgb(124, 116, 67);
    border-radius: 10px;
    margin: 40px auto;
    text-align: center;
    line-height: 100px;
    font-size: 20px;
    color: white;
    padding: 100px 0;
}
</style>