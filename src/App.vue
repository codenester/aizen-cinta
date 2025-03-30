<script setup lang="ts">
import { onMounted, ref } from 'vue';
import aizen from './assets/aizen.jpg'
import cinta from './assets/cinta.jpg'
import heart from './assets/heart.png'
const cintaClass = ref('col h-center hide cinta-hide');
const aizenClass = ref('col h-center hide');
const intro = ref("Hi");
const introClass = ref("intro-invis")
const heartClass = ref("heart-invis");
const nameClass = ref('name hide');
onMounted(() => {
  setTimeout(() => {
    introClass.value = "intro";
    setTimeout(() => {
      introClass.value = "intro-invis";
      setTimeout(() => {
        aizenClass.value = 'col h-center';
        cintaClass.value = 'col h-center cinta-hide';
        setTimeout(() => {
          intro.value = "I am Aizen";
          introClass.value = "intro";
          setTimeout(() => {
            introClass.value = "intro-invis";
            setTimeout(() => {
              cintaClass.value = 'col h-center';
              setTimeout(() => {
                intro.value = 'And she is Cinta';
                introClass.value = "intro";
                setTimeout(() => {
                  introClass.value = "intro-invis";
                  setTimeout(() => {
                    intro.value = 'She is my BUBU';
                    introClass.value = "intro";
                    setTimeout(() => {
                      introClass.value = "intro-invis";
                      setTimeout(() => {
                        intro.value = 'And I am her DUDU';
                        introClass.value = "intro";
                        setTimeout(() => {
                          introClass.value = "intro-invis";
                          setTimeout(() => {
                            heartClass.value = 'heart';
                            nameClass.value = 'name';
                          }, 2000);
                        }, 5000);
                      }, 2000);
                    }, 5000);
                  }, 2000);
                }, 5000);
              }, 2000);
            }, 2000);
          }, 5000);
        }, 2000);
      }, 2000);
    }, 5000);
  }, 50)
})
</script>

<template>
  <div class="col h-center">
    <div class="row v-center">
      <div :class="aizenClass">
        <div class="img-box">
          <img :src="aizen" alt="aizen">
        </div>
        <div :class="nameClass">Aizen</div>
      </div>
      <div :class="heartClass">
        <img :src="heart" alt="">
      </div>
      <div :class="cintaClass">
        <div class="img-box">
          <img :src="cinta" alt="cinta">
        </div>
        <div :class="nameClass">Cinta</div>
      </div>
    </div>
    <div :class="introClass">{{ intro }}</div>
  </div>
</template>

<style scoped>
.row,
.col {
  display: flex;
  transition: 2s;
  max-height: 400px;
  max-width: 800px;
  overflow: hidden;
}

.row {
  gap: 10px;
}

.col {
  flex-direction: column;
  position: relative;
  gap: 20px;
}

.row.v-center {
  align-items: center;
}

.col.h-center {
  align-items: center;
}

.intro-invis,
.intro {
  font-size: 60px;
  transition: 2s;
}

.intro-invis {
  opacity: 0.0;
}

.name {
  font-size: 40px;
  transition: 2s;
}

.name.hide {
  opacity: 0.0;
}

.img-box {
  min-width: 200px;
  min-height: 200px;
  max-width: 200px;
  max-height: 200px;
  display: flex;
  border-radius: 50%;
  position: relative;
  overflow: hidden;
  justify-content: center;
  align-items: center;
}

.col.hide {
  max-height: 0;
}

.col.cinta-hide {
  max-width: 0;
}

.heart,
.heart-invis {
  transition: .5s;
  position: relative;
  overflow: hidden;
}

.heart img {
  max-height: 100%;
  max-width: 100%;
  border-radius: 0;
}

.heart {
  display: flex;
  max-width: 80px;
  max-height: 80px;
}

.heart-invis {
  max-width: 0;
  max-height: 0;
  transform: scale(0.0);
}

img {
  max-width: calc(100% + 30px);
  max-height: calc(100% + 30px);
  border-radius: 50%;
}
</style>
