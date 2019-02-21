<template>
  <div>
    Ini Komponen User {{nomor}} <br/>
    Nama User : <br/>
    {{firstName}}
    {{lastName}}
  </div>
</template>

<script>
export default{
  name: 'User',
  props: [
    'nomor',
    'firstName',
    'lastName'
  ]
}
</script>

<style scoped>

</style>
