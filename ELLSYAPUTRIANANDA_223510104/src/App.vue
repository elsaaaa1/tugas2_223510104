<template>
  <div class="ellsyah">
    <h1>ellsyah putri ananda</h1>
    <div>
      <p>Nama:</p>
      <input type="text" v-model="nama" :style="{ 'background-color': buttonBackgroundColor }" @blur="updateText('nama')">
      <p class="input-info">Panjang maksimum teks: 10 teks </p>
      <p>Nilai input teks: <span :class="{ 'red-text': isRed }">{{ nama }}</span></p>
    </div>
    <div>
      <p>Npm:</p>
      <input type="text" v-model="npm" :style="{ 'background-color': buttonBackgroundColor }" @blur="updateText('npm')">
      <p class="input-info">Panjang maksimum teks: 10 teks </p>
      <p>Nilai input teks: <span :class="{ 'red-text': isRed }">{{ npm }}</span></p>
    </div>
    <button :style="{ 'background-color': buttonBackgroundColor }" @click="changeColor">Ubah Warna Latar Belakang Tombol</button>
    <br>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nama: '',
      npm: '',
      isRed: false,
      buttonBackgroundColor: '#3498db',
    }
  },
  methods: {
    updateText(field) {
      if (this[field].length > 10) {
        this.isRed = true;
      } else {
        this.isRed = false;
      }
    },
    changeColor() {
      this.buttonBackgroundColor = 'yellow';
    },
  }
}
</script>

<style scoped>
/* CSS Styles */
.ellsyah{
  background-image: url('./src/assets/1.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1 {
  color: #333;
  text-decoration: line-through;
  height: 10%;
}

p {
  color: #555;
  margin-bottom: 5px;
  text-align: left;
}

input[type="text"] {
  width: 20%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  box-sizing: border-box;
  z-index: 2; 
}

.input-info {
  font-size: 14px;
  color: #999;
  margin-top: -10px;
  margin-bottom: 10px;
}

span {
  font-size: 18px;
  color: #333;
  font-weight: bold;
}

.red-text {
  color: red;
}

button {
  padding: 5px 5px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 2px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #2980b9;
}
</style>
