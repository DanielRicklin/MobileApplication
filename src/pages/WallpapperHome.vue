<template>

</template>

<script>
import Wallpapper from './Wallpapper.vue';

export default {
  data() {
    return {
     
    }
  },
  beforeCreate(){
    this.$store.commit('navigator/push', {
        extends: Wallpapper,
        data() {
          return {
            toolbarInfo: {
              backLabel: 'Home',
              title: 'Fond d\'écran'
            }
          }
        }
      });
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
