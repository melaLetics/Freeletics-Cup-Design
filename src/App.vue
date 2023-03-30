<template>
  <div>
    <div class="wrapper">
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
          Challenge accepted
        </div>
      </div>  
      <div class="logo">
        <img src="@/assets/images/Freeletics.png" width="350px"/>
      </div>
      <div class="username">
        BOOTCAMP 2023 - JAY LETICS
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
    };
  },
  mounted() {

  },
  computed: {
  },
  methods: {
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
  width: 869px;
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
  display: flex;
  text-align: center;
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
  font-size: 30px;
}

.logo{
  padding: 10px;
  margin-bottom: 10px;
  text-align: center;
}

.username {
  text-align: right;
}
</style>
