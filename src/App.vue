<template>
  <div>
    <div id="scene">
      <div id="carousel" :style="style">
        <div class="carousel__cell">1</div>
        <div class="carousel__cell">2</div>
        <div class="carousel__cell">3</div>
        <div class="carousel__cell">4</div>
        <div class="carousel__cell">5</div>
        <div class="carousel__cell">6</div>
        <div class="carousel__cell">7</div>
        <div class="carousel__cell">8</div>
        <div class="carousel__cell">9</div>
      </div>
    </div>

    <div id="carousel-options">
      <p>
        <button id="previous-button" @click="prev">Previous</button>
        <button id="next-button" @click="next">Next</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  mounted: function() {},
  data: () => {
    return {
      style: "",
      input: "",
      currdeg: 0,
      carousel: null,
      vORh: "Y"
    };
  },
  methods: {
    setHV: function() {
      alert(JSON.stringify(document.getElementById("horizontal")));
      if (document.getElementById("horizontal")) {
        this.vORh = "Y";
      } else {
        this.vORh = "X";
      }
    },
    say: function(message) {
      alert(message);
    },
    next: function() {
      this.input = "n";
      this.rotate();
    },
    prev: function() {
      this.input = "p";
      // alert(this.currdeg);
      this.rotate();
    },
    rotate: function() {
      if (this.input == "n") {
        this.currdeg = this.currdeg - 40;
      }
      if (this.input == "p") {
        this.currdeg = this.currdeg + 40;
      }
      if (this.input != "") {
        this.carousel = document.getElementById("carousel");
        // alert(JSON.stringify(this.carousel));
        this.style = {
          "-webkit-transform": "rotateY(" + this.currdeg + "deg)",
          "-moz-transform": "rotateY(" + this.currdeg + "deg)",
          "-o-transform": "rotateY(" + this.currdeg + "deg)",
          transform: "rotateY(" + this.currdeg + "deg)"
        };
      } else {
        this.style = "";
      }
      this.input = "";
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  text-align: center;
}

#scene {
  /* border: 1px solid #ccc; */
  margin: 40px 0;
  position: relative;
  width: 210px;
  height: 140px;
  margin: 80px auto;
  perspective: 1000px;
}

#carousel {
  width: 100%;
  height: 100%;
  position: absolute;
  transform: translateZ(-288px);
  transform-style: preserve-3d;
  transition: transform 1s;
}

.carousel__cell {
  position: absolute;
  width: 190px;
  height: 120px;
  left: 10px;
  top: 10px;
  border: 1px groove lightgray;
  border-radius: 5%;
  line-height: 116px;
  font-size: 90px;
  font-weight: bold;
  color: white;
  text-align: center;
  transition: transform 1s, opacity 1s;
}
.carousel__cell:nth-child(9n + 1) {
  background: hsla(0, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(0, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 2) {
  background: hsla(40, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(40, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 3) {
  background: hsla(80, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(80, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 4) {
  background: hsla(120, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(120, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 5) {
  background: hsla(160, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(160, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 6) {
  background: hsla(200, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(200, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 7) {
  background: hsla(240, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(240, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 8) {
  background: hsla(280, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(280, 100%, 50%, 0.8);
}
.carousel__cell:nth-child(9n + 0) {
  background: hsla(320, 100%, 50%, 0.8);
  box-shadow: 0px 0px 10px 3px hsla(320, 100%, 50%, 0.8);
}

.carousel__cell:nth-child(1) {
  transform: rotateY(0deg) translateZ(288px);
}
.carousel__cell:nth-child(2) {
  transform: rotateY(40deg) translateZ(288px);
}
.carousel__cell:nth-child(3) {
  transform: rotateY(80deg) translateZ(288px);
}
.carousel__cell:nth-child(4) {
  transform: rotateY(120deg) translateZ(288px);
}
.carousel__cell:nth-child(5) {
  transform: rotateY(160deg) translateZ(288px);
}
.carousel__cell:nth-child(6) {
  transform: rotateY(200deg) translateZ(288px);
}
.carousel__cell:nth-child(7) {
  transform: rotateY(240deg) translateZ(288px);
}
.carousel__cell:nth-child(8) {
  transform: rotateY(280deg) translateZ(288px);
}
.carousel__cell:nth-child(9) {
  transform: rotateY(320deg) translateZ(288px);
}

#carousel-options {
  text-align: center;
  position: relative;
  z-index: 2;
  background: hsla(0, 0%, 100%, 0.8);
}
</style>
