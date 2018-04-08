<template>
  <v-ons-page>
    <custom-toolbar v-bind="toolbarInfo"></custom-toolbar>

    <v-ons-carousel fullscreen swipeable auto-scroll overscrollable
      :index.sync="carouselIndex"
    >
      <v-ons-carousel-item v-for="(value, key) in items" :key="key"
        class="carousel-item"
        :style="{ backgroundImage: 'url(' + value + ')', backgroundSize: '100% 100%'}"
      >
        <div class="color-tag">{{key}}</div>
        <div class="color-tag2"><a href="#" @click="openImage(value)">Avoir l'image</a></div>
      </v-ons-carousel-item>
    </v-ons-carousel>

    <div class="dots">
      <span v-for="dotIndex in Object.keys(items).length" :key="dotIndex"
        @click="carouselIndex = dotIndex - 1"
      >
        {{ carouselIndex === dotIndex - 1 ? '\u25CF' : '\u25CB' }}
      </span>
    </div>

  </v-ons-page>
</template>

<script>
export default {
  data() {
    return {
      carouselIndex: 0,
      items: {
        nuit: 'https://c1.staticflickr.com/6/5256/5426098711_0337a689fe_b.jpg',
        lune: 'https://c1.staticflickr.com/6/5023/5629366558_c973a0a803_b.jpg',
        paysage: 'https://c1.staticflickr.com/6/5506/11521802125_25df25e8f8_b.jpg'       
      }
      //blue: '#085078',
      // dark: '#373B44',
      // orange: '#D38312'
    }
  },
  methods: {
    openImage(i){
      window.open(i, '_blank');
    }
  }
}
</script>

<style scoped>
.carousel-item {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.color-tag {
  color: rgb(206, 206, 206);
  font-size: 48px;
  font-weight: bold;
  text-transform: uppercase;
  position: absolute;
  bottom: 0px;
  left: 50%;
  transform: translate(-50%, -50%);
  display:block;
}

.color-tag2 {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, -50%);
  display:block;
}

.color-tag2 a{
  text-decoration: none;
  color: rgb(147, 212, 255);
  font-weight: bold;
}

.dots {
  text-align: center;
  font-size: 30px;
  color: #fff;
  position: absolute;
  bottom: 40px;
  left: 0;
  right: 0;
}

.dots > span {
  cursor: pointer;
}
</style>
