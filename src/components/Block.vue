<template>
    <div @click="stoptimer" v-if="showblock" class="block   mx-auto mt-5 bg-blue-500 w-[400px] h-[300px] rounded-md">
        <div class="h-full flex flex-col justify-center ">
            <h1 class="text-center text-sm text-white font-bold ">click me</h1>
        </div>
    </div>
</template>

<script>
export default {
    props: ['dt'],
    data() {
        return {
            showblock: false,
            score: 0,
            timer: null,
            
        }
    },
    methods: {
        starttimer() {
            this.timer = setInterval(() => {
                this.score += 50
            }, 50);
        },
        stoptimer() {
            clearInterval(this.timer)
            console.log(this.score)
            this.$emit("endgame", this.score)
        }
    },
    mounted() {
        setTimeout(() => {
            this.showblock = true;
            this.starttimer()
        }, this.dt);

    },

    updated() {
        console.log("this is update ")
    },

}
</script>

<style>

</style>