<!-- <script setup>
import axios from 'axios';
import { onMounted } from 'vue';
import { ref } from 'vue';
import router from './router';
// Your setup code here
const apiData = ref([]);

// Make an API request when the component is mounted
onMounted(async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/users');
    console.log(response.data);
    apiData.value = response.data;
  } catch (error) {
    console.error('Error fetching data from the API:', error);
  }
});
const navigateToAbout = (itemId) => {
  // Use router.push to navigate to the dynamic route
  router.push(`/about/${itemId}`);
};
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

    <template>

    </template>
  </header>
  <!-- <RouterView /> -->
</template>

<style scoped>
.get {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  flex-wrap: wrap;
  gap: 5px;
  padding: 20px;
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
}
</style> -->
