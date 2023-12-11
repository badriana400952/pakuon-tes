

<script setup>
import axios from 'axios';
import { onMounted, ref } from 'vue';
import router from './router';

const patternRows = ref([]);
const apiData = ref([]);

function generatePattern(n) {
  for (let i = 1; i <= n; i++) {
    let row = '';
    for (let j = 1; j <= n + 3; j++) {
      row += j;
      if (i === j) {
        row += '**';
        j += 2;
      }
    }
    patternRows.value.push(row);
  }
}

const n = parseInt(prompt("Input n: "));
generatePattern(n);

const navigateToAbout = (itemId) => {
  router.push(`/about/${itemId}`);
};

onMounted(async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/users');
    apiData.value = response.data;
  } catch (error) {
    console.error('Error fetching data from the API:', error);
  }
});
</script>


<template>
  
  <header>
    <div class="satu">
      <div class="aa">
        <div class="satus">1</div>
        <div class="dua">
          <div class="duaa">2</div>
          <div class="duab">3</div>
        </div>
        <div class="box4">
          <div class="empata">
            <div class="empat">4</div>
            <div class="delapan">
              <div class="delapanA">8</div>
              <div class="delapanB">9</div>
              <div class="delapanC">10</div>
            </div>
          </div>
          <div class="lima">
            <div>5</div>
            <div>6</div>
            <div>7</div>
          </div>
        </div>
      </div>
    </div>


    <div class="get">
      <div class="card" v-for="item in apiData" :key="item.id">
        <Text>{{ item.name }}</Text>
        <Button type="primary" @click="navigateToAbout(item.id)">Show</Button>
      </div>
    </div>

    <div class="erdtes">
      <p>
        erd test
      </p>
      <div v-for="(row, index) in patternRows" :key="index">
        {{ row }}
      </div>
    </div>


    <div class="jelaskan">
      <h2>F.Jelaskan istilah dibawah dengan bahasa sendiri </h2>
      <p>
        <strong>Cypress:</strong> Cypress adalah sebuah alat pengujian (testing tool) yang digunakan dalam pengembangan
        perangkat lunak. Cypress memungkinkan para pengembang untuk melakukan pengujian otomatis pada aplikasi web dengan
        mudah dan efisien.
      </p>

      <p>
        <strong>Kubernetes:</strong> Kubernetes adalah platform open-source untuk mengelola, merancang, dan menyebarkan
        aplikasi dalam kontainer. Ini membantu otomatisasi proses pengelolaan aplikasi, termasuk penyebaran, skalabilitas,
        dan manajemen sumber daya.
      </p>

      <p>
        <strong>ORM (Object-Relational Mapping):</strong> ORM adalah teknik atau metode dalam pengembangan perangkat lunak
        yang memungkinkan pemetaan antara struktur data dalam basis data relasional dan objek dalam bahasa pemrograman
        yang digunakan.
      </p>

      <p>
        <strong>Class:</strong> Class adalah konstruksi dasar dalam pemrograman berorientasi objek (OOP). Ini adalah
        blueprint atau cetak biru untuk membuat objek, yang mendefinisikan atribut (data) dan metode (fungsi) yang
        dimiliki oleh objek tersebut.
      </p>

      <p>
        <strong>Function:</strong> Fungsi (function) adalah blok kode yang dirancang untuk melakukan tugas tertentu dan
        dapat dipanggil oleh bagian lain dari program. Fungsi membantu dalam mengorganisasi dan memisahkan logika program
        untuk membuatnya lebih mudah dipahami dan dikelola.
      </p>

      <p>
        <strong>DevOps:</strong> DevOps adalah praktik kolaboratif yang menggabungkan pengembangan (development) dan
        operasi (operations) dalam siklus hidup pengembangan perangkat lunak. Tujuannya adalah untuk meningkatkan
        koordinasi dan efisiensi antara tim pengembangan dan operasional.
      </p>

      <p>
        <strong>Docker:</strong> Docker adalah platform perangkat lunak yang memungkinkan pengembang untuk mengemas,
        mendistribusikan, dan menjalankan aplikasi dalam lingkungan yang terisolasi yang disebut kontainer. Kontainer
        memungkinkan aplikasi untuk berjalan konsisten di berbagai lingkungan, mulai dari lingkungan pengembangan hingga
        produksi.
      </p>
    </div>

    <div class="jelaskan">
      <h2>G.Microservices Architecture:</h2>
    <p>
        <strong>Teknologi Terbaik:</strong> Kubernetes sebagai orchestrator, Spring Boot untuk pengembangan mikroservis.
    </p>
    <p>
        <strong>Alasan:</strong> Microservices memungkinkan pembangunan aplikasi yang terdiri dari sejumlah kecil layanan independen yang dapat dikelola dan ditingkatkan secara terpisah. Kubernetes sebagai orchestrator membantu dalam manajemen, otomatisasi, dan penyebaran mikroservis. Spring Boot adalah kerangka kerja yang ringan dan kuat untuk mengembangkan mikroservis dengan cepat.
    </p>

    <h5>Serverless Architecture:</h5>
    <p>
        <strong>Teknologi Terbaik:</strong> AWS Lambda, Azure Functions, atau Google Cloud Functions.
    </p>
    <p>
        <strong>Alasan:</strong> Arsitektur serverless memungkinkan pengembang untuk fokus pada logika bisnis tanpa harus mengelola infrastruktur server. Fungsi dapat dijalankan secara otomatis sesuai kebutuhan dan hanya saat diperlukan, mengurangi biaya operasional. AWS Lambda, Azure Functions, dan Google Cloud Functions adalah platform serverless yang populer dan menyediakan dukungan untuk berbagai bahasa pemrograman.
    </p>

    <h5>Single Page Application (SPA) Architecture:</h5>
    <p>
        <strong>Teknologi Terbaik:</strong> ReactJS (dengan Redux atau Context API) atau Angular.
    </p>
    <p>
        <strong>Alasan:</strong> SPA memungkinkan pengalaman pengguna yang responsif dan cepat dengan memuat satu halaman utama dan mengganti kontennya secara dinamis tanpa memuat ulang seluruh halaman. ReactJS dan Angular adalah dua kerangka kerja JavaScript yang populer untuk mengembangkan SPA. ReactJS dikenal karena fleksibilitasnya dan dapat diintegrasikan dengan berbagai teknologi, sedangkan Angular menyediakan pendekatan yang lebih terstruktur dengan banyak fitur bawaan.
    </p>
    </div>

    <div class="image">
      <img src="./assets/erd.png" alt="Logo"/>
  </div>
  </header>
</template>

<style scoped>
.image{
  width: 500px;
  height: 500px;
}
.erdtes {
  margin: 20px auto;
  margin-left: 20px;
}

.get {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  flex-wrap: wrap;
  gap: 5px;
  padding: 20px;
}

.jelaskan {
  width: 800px;
  margin: 20px auto;
}

.card {
  width: 500px;
  line-height: 40px;
  border-radius: 7px;
  display: flex;
  justify-content: space-between;
  padding: 5px;
  background-color: red;
}

.aa {
  width: 100%;
}

.empata {
  display: flex;
  width: 60%;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.satus {
  background-color: blue;
  text-align: center;
  padding: 20px;
}

.satu {
  max-width: 1400px;
  background-color: aqua;
  text-align: center;
  padding: 20px;
  margin: auto;
}

body {
  padding: 20px;
}

.dua {
  display: flex;
  justify-content: space-around;
  text-align: center;
  flex: 3;
  width: 100%;
}

.duaa {
  border: 1px solid white;
  background-color: rgb(53, 53, 223);
  width: 100%;
  padding-top: 20px;
}

.duab {
  border: 1px solid white;
  background-color: rgb(29, 29, 122);
  width: 100%;
  padding-top: 20px;
  text-align: center;
}

.box4 {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  width: 100%;
  margin-top: 2px;
  padding-bottom: 10px;
}

.empat {
  padding-top: 20px;
  padding-bottom: 20px;
  border: 2px solid white;
  width: 100%;
  height: 200px;
}

.lima {
  width: 39%;
  padding-top: 4px;
  height: 234px;
  padding-left: 4px;
  padding-right: 4px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-around;
}

.lima div {
  width: 100%;
  border: 2px solid white;
  flex: 1;
}

.delapan {
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex: 1;
  width: 100%;
  gap: 4;
  padding-top: 20px;
  padding-bottom: 20px;
  margin-top: 2px;
}

.delapanA {
  width: 100%;
  border: 1px solid white;
  padding-top: 20px;
}

.delapanB {
  width: 100%;
  border: 1px solid white;
  padding-top: 20px;
}

.delapanC {
  width: 100%;
  border: 1px solid white;
  padding-top: 20px;
}

@media (max-width: 567px) {
  .aa {
    background-color: gray;
    text-align: center;
  }

  .dua {
    flex-direction: column;
  }

  .box4,
  .empata {
    flex-direction: column;
  }

  .lima {
    width: 100%;
  }
}</style>
