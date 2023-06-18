<template>
  <div>
    <FormSiswa @siswa-added="updateDaftarSiswa"></FormSiswa>
    <DaftarSiswa :siswa-baru="siswaBaru"></DaftarSiswa>
  </div>
</template>

<script>
//import 'bootstrap/dist/css/bootstrap.css'
//import 'bootstrap-vue/dist/bootstrap-vue.css'
import FormSiswa from './component/FormSiswa';
import DaftarSiswa from './component/DaftarSiswa';

export default {
  components: {
    FormSiswa,
    DaftarSiswa
  },
  data() {
    return {
      siswaBaru: null
    };
  },
  methods: {
    updateDaftarSiswa(siswa) {
      this.siswaBaru = siswa;
    }
  }
};
</script>
