<template>
  <div class="hello">
    <h1>Selamat Mengerjakan</h1>
    <p :style="'color: red'" v-if="poin < items.length-((items.length*3)/10)">Maaf, Anda Belum berhasil.</p>
    <p :style="'color: green'" v-else>Selamat, Anda berhasil</p>
    <p>{{ 'Poin Anda '+poin}}</p>
    <div v-for="(item,index) in items" :key="item.pertanyaan" :options="item.pertanyaan">
      <p>{{index+1}}. {{ item.pertanyaan}}</p>
      <div  v-for="pilih in item.pilihan" :key="pilih.pilihan" :options="pilih.pilihan">
        <input type="radio"  :name="'name'+index"
         @click="checkJawaban(index,pilih.pilihan)"
        :value="pilih.pilihan" >{{ pilih.pilihan }}
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  data: function(){
    return {
      nama: 'Dimas',
      show: true,
      poin:0,
      jawabanbenar: [],
      items:[
        {
          name: 'soal1',
          pertanyaan: 'Jumlah anak yang ada di kelas XII RPL 2 ?',
          answer:String,
          check:true,
          pilihan:[
            { pilihan: '26' },
            { pilihan: '36' },
            { pilihan: '16'},
            { pilihan: '46' }
          ],
          jawaban: '36'
        },
        {
          pertanyaan: 'Anak perempuan di kelas XII RPL 2 ?',
          name: 'soal2',
          check:true,
          answer:String,
          pilihan:[
            { pilihan: '2' },
            { pilihan: '1' },
            { pilihan: '3' },
            { pilihan: '4' }
          ],
          jawaban: '2'
        },
        {
          pertanyaan: 'Anak Laki - laki di kelas XII RPl 2?',
          answer:String,
          check:true,
          name: 'soal3',
          pilihan:[
            { pilihan: '28' },
            { pilihan: '34' },
            { pilihan: '36' },
            { pilihan: '75' }
          ],
          jawaban: '36'
        },
        {
          pertanyaan: 'Wali kelas XII RPL 2 ?',
          answer:String,
          check:true,
          name: 'soal3',
        pilihan:[
            { pilihan: 'Bu Dini ?' },
            { pilihan: 'Bu Arne' },
            { pilihan: 'Pak Jajat' },
            { pilihan: 'Pak Ujang' }
          ],
          jawaban: 'Bu Dini'
        },
        {
          pertanyaan: 'Berapa jumlah roda motor?',
          answer: String,
          check: true,
          name: 'soal3',
          pilihan:[
            { pilihan: '1' },
            { pilihan: '2' },
            { pilihan: '3' },
            { pilihan: '4' }
          ],
          jawaban: '2'
        }
      ]
    }
  },
  methods: {
    hideTitle () {
      this.show = !this.show
    },
    checkJawaban(i,jawab){

      if(this.items[i].jawaban === jawab){
        if(this.jawabanbenar.indexOf(i) == -1){
          this.poin++;
          this.jawabanbenar.push(i);
        }
      }
      if(this.items[i].jawaban !== jawab){
        if(this.jawabanbenar.indexOf(i) != -1){
          this.poin--;
          this.jawabanbenar.splice(this.jawabanbenar.indexOf(i), 1);
        }
      }

        this.items[i].check = false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
