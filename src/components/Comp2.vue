<template>
  <div>
    <User v-for="(User, index) in users"
          :nomor="User.nomor"
          :firstName="User.firstName"
          :lastName="User.lastName"
          :key="index"></User>
    <input type="text" v-model="Name">
    <Quiz :Name="Name"></Quiz>
    <p v-for="(Soal, index) in soal"
      :key="index">
      {{Soal.pert}}
    </p>
  </div>
</template>

<script>
import User from '@/components/User'
import Quiz from '@/components/Quiz'
export default {
  name: 'Comp2',
  components: {
    User,
    Quiz
  },
  data () {
    return {
      msg: 'Welcome to Your Uvuvwevwevwe Onyetenyevwe Ossas',
      users: [
        {
          nomor: 1,
          firstName: 'AAA',
          lastName: 'aBBBrray2'
        },
        {
          nomor: 2,
          firstName: 'UUU',
          lastName: 'aBBBrray2'
        }
      ],
      Name: '',
      soal: [
        {
          id: 1,
          pert: 'ASU ADALAH?!!'
        }
      ]
    }
  },
  methods: {
    addnumber () {
      this.number++
    }
  },
  mounted () {
    this.number = 200
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
