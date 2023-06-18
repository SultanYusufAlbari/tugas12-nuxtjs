<template>
  <div>
    <FormSiswa @siswa-added="updateDaftarSiswa"></FormSiswa>
    <DaftarSiswa :siswa-baru="siswaBaru"></DaftarSiswa>
  </div>
</template>

<script>
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
