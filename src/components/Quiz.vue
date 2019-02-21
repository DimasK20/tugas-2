<template>
  <div>
    <p v-for="(Soal, index) in materis"
            :key="index">
            {{Soal.soal.soal}}></p>
    <h1>Quiz Pakrampak</h1>
  </div>
</template>

<script>
export default{
  name: 'User',
  props: [
    'Name'
  ],
  materis: [
    {
      soal:
        {
          id: 1,
          soal: 'ASU ADALAH?!!'
        }
    }
  ]
}
</script>

<style scoped>

</style>
