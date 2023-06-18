<template>
    <div>
      <h2>Daftar Siswa</h2>
      <ul>
        <li v-for="(siswa, index) in daftarSiswa" :key="index">
          No Induk: {{ siswa.induk }} - Nama: {{ siswa.nama }} - Nilai: {{ siswa.nilai }}
        </li>
      </ul>
      <h3>Rata-rata Nilai Tugas: {{ rataRataNilai }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      siswaBaru: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        daftarSiswa: []
      };
    },
    computed: {
      rataRataNilai() {
        if (this.daftarSiswa.length === 0) {
          return 0;
        }
        const totalNilai = this.daftarSiswa.reduce((sum, siswa) => sum + siswa.nilai, 0);
        return (totalNilai / this.daftarSiswa.length).toFixed(2);
      }
    },
    watch: {
      siswaBaru(newSiswa) {
        this.daftarSiswa.push(newSiswa);
      }
    }
  };
  </script>
  