<script>


export default{
  data(){
    return{
      namapengadu: "Belum ada data",
      keluhpengadu: "Belum ada data"
    }
  },
  created(){
    this.sambutan(),
    this.isi()
  },
  methods:{
    sambutan(){
      alert("Selamat Datang");
    },
    isi(){
      alert("Helpdesk");
    },
    async upnama(){
      const data = await fetch("http://127.1.0.1:82/namapengadu")
      const datanya = await data.json()
      this.namapengadu = datanya.namajs
    },
    async upkeluh(){
      const data = await fetch("http://127.1.0.1:82/keluhpengadu")
      const datanya = await data.json()
      this.keluhpengadu = datanya.keluhjs
    }
  }
}
//tempat ngoding javascript
</script>

<template>
<!----tempat ngoding html-->
  <div>  Nama pengadu = {{ namapengadu }} </div>
  <div> Keluhan = {{ keluhpengadu }} </div>
  <button @click="upnama" >Ambil Data Nama</button>
  <button @click="upkeluh" >Ambil Data Keluhan</button>

</template>

