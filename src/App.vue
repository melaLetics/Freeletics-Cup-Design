<template>
  <div>
    <div id="capture" class="wrapper">
      <div class="multiline">
        <div class="slogan-1">THIS COULD BE THE FIRST LINE</div>
        <div class="slogan-2">IF THERE ARE TWO LINES IN SLOGAN</div>
      </div>
      <div class="singleline">
        <div class="slogan">Challenge accepted</div>
      </div>
      <div class="logo">
        <img
          src="@/assets/images/cat1.jpg"
          width="120px"
          style="margin-right: -10px"
        />
        <img
          src="@/assets/images/Freeletics_Logo_RGB_White.png"
          width="150px"
          style="padding-right: 20px; padding-bottom: 25px"
        />
        <img
          src="@/assets/images/cat2.jpg"
          width="120px"
          style="margin-left: -20px"
        />
      </div>
      <div class="username">BOOTCAMP 2023 - JAY LETICS</div>
    </div>
    <button @click="downloadImage">Download as image</button>
  </div>
</template>

<script>
import domtoimage from 'dom-to-image-more';

export default {
  name: 'App',
  data() {
    return {};
  },
  mounted() {},
  computed: {},
  methods: {
    downloadImage() {
      domtoimage
        .toPng(document.getElementById('capture'))
        .then(function (dataUrl) {
          var img = new Image();
          img.src = dataUrl;
          document.body.appendChild(img);
        })
        .catch(function (error) {
          console.error('oops, something went wrong!', error);
        });
    },
  },
};
</script>

<style>
@font-face {
  font-family: 'TheSans';
  src: local('TheSans'),
    url(./assets/fonts/TheSansBlackPlain.ttf) format('truetype');
}
.wrapper {
  height: 335px;
  width: 869px;
  padding-left: 30px;
  padding-right: 45px;
  padding-bottom: 20px;
  background-color: black;
  color: white;
  font-family: 'TheSans', Helvetica, Arial;
  font-size: 20px;
}

/* just choose display: flex to use multiline slogan*/
.multiline {
  display: none;
}

/* choose display: none to use multiline slogan*/
.singleline {
  display: flex;
  text-align: center;
}

.slogan-1 {
  padding-top: 20px;
}

.slogan-2 {
  width: 869px;
  text-align: right;
  margin-bottom: 5px;
}

.slogan {
  padding-top: 20px;
  font-size: 30px;
}

.logo {
  padding: 10px;
  margin-bottom: 10px;
  text-align: center;
}

.username {
  padding-right: 55px;
  text-align: right;
}
</style>
