<template>
  <p>Result is : {{ score }}ms</p>
  <h3 v-if="score<250">You are too fast.</h3>
  <h3 v-else-if="score>250 && score<500">You are normal.</h3>
  <h3 v-else>You are too slow. Try again!</h3>
</template>

<script>
export default {
    name : 'app',
    props : [
        'score'
    ]
}
</script>

<style>

</style>