<template>
  <div>
    <div id="capture" class="wrapper">
      <div class="multiline">
        <div class="slogan-1">
          THIS COULD BE THE FIRST LINE 
        </div>
        <div class="slogan-2">
                IF THERE ARE TWO LINES IN SLOGAN
        </div>
      </div>
      <div class="singleline">
        <div class="slogan">
          WE DON'T STOP WHEN IT HURTS, WE STOP WHEN WE ARE DONE.
        </div>
      </div>  
      <div class="logo">
        <img src="@/assets/images/Freeletics_Logo_RGB_White.png" width="150px" style="padding-right: 20px; padding-bottom: 25px;"/>
        <img src="@/assets/images/unicorn_white.svg" width="200px" />
      </div>
      <div class="username">
        BOOTCAMP 2022 - SARAH LETICS
      </div>
    </div>
    <button @click="downloadImage">
       Download as image 
    </button>
  </div>
</template>

<script>

import domtoimage from "dom-to-image-more";

export default {
  name: 'App',
  data() {
    return {
    };
  },
  mounted() {
      this.print();
  },
  computed: {
  },
  methods: {
    downloadImage(){
      domtoimage
      .toPng(document.getElementById("capture"))
      .then(function (dataUrl) {
        var img = new Image();
        img.src = dataUrl;
        document.body.appendChild(img);
      })
      .catch(function (error) {
        console.error("oops, something went wrong!", error);
      });
    }
  }
};
</script>

<style>
@font-face {
  font-family: "TheSans";
  src: local("TheSans"), url(./assets/fonts/TheSansBlackPlain.ttf) format("truetype");
}
.wrapper {
  height: 335px;
  width: 840px;
  padding-left: 30px;
  padding-right: 45px;
  padding-bottom: 20px;
  background-color: black;
  color: white;
  font-family: "TheSans", Helvetica, Arial;
  font-size: 20px;
}

/* just choose display: flex to use multiline slogan*/
.multiline{
  display: none;
}

/* choose display: none to use multiline slogan*/
.singleline{
  /*display: flex;*/
  text-align: left;
}

.slogan-1{
  padding-top: 20px;
}

.slogan-2 {
  width: 869px;
  text-align: right;
  margin-bottom: 5px;
}

.slogan {
  padding-top: 20px;
  padding-left: 5px;
  margin-bottom: 15px;
  font-size: 28px;
}

.logo{
  margin: 5px;
  padding: 5px;
  text-align: center;
}

.username {
  margin-top: 15px;
  text-align: right;
  font-size: 28px;
  padding-right: 5px;}
</style>
