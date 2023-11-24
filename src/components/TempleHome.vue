<template>
  <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      style="text-shadow: 1px 1px 2px #333"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        class="car-slide"
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
      >
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            src="../assets/Temple1.jpg"
            alt="image slot"
          />
        </template>
      </b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide
        class="car-slide"
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
      >
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            src="../assets/Temple2.jpg"
            alt="image slot"
          />
        </template>
      </b-carousel-slide>

      <b-carousel-slide class="car-slide">
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            src="../assets/Temple1.jpg"
            alt="image slot"
          />
        </template>
      </b-carousel-slide>

      <!-- Slide with blank fluid image to maintain slide aspect ratio -->
      <b-carousel-slide
        class="car-slide"
        caption="Blank Image"
        img-blank
        img-alt="Blank image"
      >
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse
          eros felis, tincidunt a tincidunt eget, convallis vel est. Ut
          pellentesque ut lacus vel interdum.
        </p>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script scoped>
export default {
  name: "TempleHome",
  data() {
    return {
      slide: 0,
      sliding: null,
    };
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    },
  },
};
</script>
<style>
.car-slide {
  height: 80vh;
}
.img-fluid {
  object-fit: cover;
  height: 100%;
}
</style>
