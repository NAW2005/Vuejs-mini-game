<template>
    <div>
        <p class=" text-center mt-4">Result is {{ score }} ms </p>
    </div>
    <div class=" text-center mt-4">
        <div v-if="score <= 250">
            <p class="text-blue-400 ">omg u r god of catching </p>
        </div>
        <div v-else-if="score > 250 && score <= 500">
            <p class="text-blue-400 ">You are normal</p>
        </div>
        <div v-else>
            <p class="text-blue-400 ">slow man!catch me fast </p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['score']

}
</script>

<style>

</style>