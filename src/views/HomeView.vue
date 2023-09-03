<template>
  <div class="home bg-grey-3">
    <div class="d-flex items-center justify-center full-height bg-dark">
      <div class="text-white" id="typewriter"></div>

      <q-carousel
          animated
          v-model="slide"
          class="carousel"
          arrows
          navigation
          infinite
          autoplay
          :transition-duration="1000"
      >
        <q-carousel-slide :name="1" img-src="https://sun9-26.userapi.com/impf/c845416/v845416138/5124b/lWdQ3yj6BRo.jpg?size=1536x2048&quality=96&sign=7cf3e9c94ff861eee13d0d24a66f8f14&type=album" />
        <q-carousel-slide :name="2" img-src="https://sun9-33.userapi.com/impf/c639126/v639126750/f439/tbW1XCED__M.jpg?size=1280x960&quality=96&sign=c5992d926f2ef116a018f3de970ced75&type=album" />
        <q-carousel-slide :name="3" img-src="https://sun9-6.userapi.com/impg/PfhRoLcbcUkvrmAj0kTstx5MFmP3IrpyUYdDoQ/upPmF5WiIKU.jpg?size=912x1080&quality=96&sign=95aca616074d97e477070ddb6cbf5812&type=album" />
      </q-carousel>
    </div>
  </div>
</template>

<script setup>
import Typewriter from 'typewriter-effect/dist/core';
import {onMounted, nextTick, ref} from "vue";

const slide = ref(1)

onMounted(async () => {
  await nextTick(() => {
    const typewriter = new Typewriter('#typewriter', {
      loop: true,
      delay: 75,
    });

    typewriter
        .pauseFor(1500)
        .typeString('Привет! Я Алексей Огневой и я Frontend Developer')
        .pauseFor(2000)
        .deleteAll()
        .typeString('Мне 24 года, пишу на <span class="text-positive text-bold">Vue.js</span> ' +
            '<span class="text-secondary text-bold">Nuxt</span> ' +
            '<span class="text-primary text-bold">Quasar</span>')
        .pauseFor(2000)
        .deleteAll()
        .deleteAll()
        .typeString('С программированием столкнулся в институте и влюбился в это дело')
        .pauseFor(2000)
        .typeString('Если тебе интересно и хочешь научиться также, то пройди тестовое задание')
        .pauseFor(2000)
        .deleteAll()
        .typeString('P.S. из меня так себе дизайнер')
        .pauseFor(2000)
        .deleteAll()
        .start();
  })

})
</script>

<style lang="scss">
$headerHeight: 50px;
$typewriterHeight: 27px;

.home{
  height: calc(100vh - #{$headerHeight});

  #typewriter{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: #{$typewriterHeight};

    .Typewriter__wrapper{
      font-size: 18px;
      font-weight: 500;
    }
  }

  .carousel{
    height: calc(100vh - #{$headerHeight} - #{$typewriterHeight});
  }
}
</style>
