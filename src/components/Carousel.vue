<template>
  <div class="carousel-section">
    <button @click="prev()" type="button" class="btn btn-left">
      <img src="../assets/left-arrow.png" class="icone" alt="" />
    </button>
    <div class="container">
      <div
        class="container-slider"
        :style="{
          transform: `translateX(${index}vw)`,
          transition: `${transition}`,
        }"
      >
        <div class="slide">
          <img src="../assets/img1.jpg" class="slide-picture" alt="img1" />
        </div>
        <div class="slide">
          <img src="../assets/img2.jpg" class="slide-picture" alt="img2" />
        </div>
        <div class="slide">
          <img src="../assets/img3.jpg" class="slide-picture" alt="img3" />
        </div>
        <div class="slide">
          <img src="../assets/img4.jpg" class="slide-picture" alt="img4" />
        </div>
        <div class="slide">
          <img src="../assets/img5.jpg" class="slide-picture" alt="img5" />
        </div>
        <div class="slide">
          <img src="../assets/img6.jpg" class="slide-picture" alt="img6" />
        </div>
      </div>
      <button @click="next()" type="button" class="btn btn-right">
        <img src="../assets/right-arrow.png" class="icone" alt="" />
      </button>
    </div>
    <div class="dots">
      <input type="radio" id="radio1" />
      <input type="radio" id="radio2" />
      <input type="radio" id="radio3" />
      <input type="radio" id="radio4" />
      <input type="radio" id="radio5" />
      <input type="radio" id="radio6" />
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      index: 0,
      transition: "transform 0.2s ease",
    };
  },
  methods: {
    prev() {
      if (this.index === 0) {
        this.transition = "none";
        this.index = -500;
      } else {
        this.transition = "transform 0.2s ease";
        this.index += 100;
      }
    },
    next() {
      if (this.index === -500) {
        this.transition = "none";
        this.index = 0;
      } else {
        this.transition = "transform 0.2s ease";
        this.index -= 100;
      }
    },
  },
};
</script>

<style>
.carousel-section {
  background: #a7c7e7;
  position: relative;
  margin: 5vh 0 2vh 0;
  overflow: hidden;
}
.container-slider {
  display: flex;
  align-items: flex-start;
  width: 600vw;
  height: 65vw;
  overflow: hidden;
}
.slides-container {
  display: flex;
  width: 100%;
}
.slide {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100vw;
}
.slide-picture {
  background: white;
  width: 100vw;
  object-fit: cover;
}
.btn {
  outline: none;
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 100%;
  position: absolute;
  display: block;
  z-index: 1000;
  transform: translateY(-50%);
  display: flex;
  justify-content: center;
  align-items: center;
  background: black;
  padding: 0;
  cursor: pointer;
}
.btn-left {
  top: 50%;
  left: 1vw;
}
.btn-right {
  top: 50%;
  right: 1vw;
}
.icone {
  width: 25px;
}
@media (max-width: 767px) {
  .slide {
    width: 100vw;
    margin: 0;
  }
  .container {
    display: flex;
    align-items: flex-start;
    width: 600vw;
    height: auto;
    transform: none;
  }
  .container-slider {
    width: 600vw;
    overflow-x: scroll;
  }
  .slide-picture {
    width: 100vw;
  }
}
</style>

