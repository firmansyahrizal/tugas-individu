<script>
export default {
  data(){
    return{
      zaka: '20',
      riya: '40'
    }
  },
  created(){
    this.getData2()
  },
  methods: {
    getData(){
      this.zaka = 60
    },
    async getData2(){
      const response = await fetch('http://localhost:82/riya1');
      const data = await response.json();
      this.nama = data.xd
      console.log(data)
    }
  }
}
</script>

<template>
  <div>hello-zaka {{ zaka }} {{ riya }}</div>
  <button @click="getData" class="bg-blue-300 p-2 rounded-3xl">Ubah</button>
  <button @click="getData2" class="bg-red-500 p-5 rounded-sm">Ambil</button>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
