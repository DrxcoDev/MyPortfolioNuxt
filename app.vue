

<template>
  <body style="background: black;color: white;">
    <div style="margin-top: 200px;">
      <h1 align="left" class="h1-title" style="font-size: 60px;margin-left: 400px;">FullStack Developer</h1>
      <h1 align="left" class="h1-title" style="font-size: 60px;margin-left: 400px;">I am Drxco</h1>
    </div>
    
  </body>
  <div style="margin-top: 500px;margin-bottom: 200px;margin-left: 200px;">
      <h1 align="left" class="h1-title" style="font-size: 60px;width: auto;">About me</h1>
      <p style="font-size: 20px;width: 500px;">Hello, I'm Drxco, well that's my first name. I live in the city of Valencia, Spain. I am currently trained as a fullstack developer.</p>
      <div style="display: flex;margin-top: 20px;">
        <UButton color="red" variant="outline">Projects</UButton>
        <UButton color="red" variant="outline" style="margin-left: 38px;">Experience</UButton>
        <UButton
          style="margin-left: 38px;"
          size="sm"
          color="red"
          square
          variant="solid"
        >
          <template #leading>
            <UAvatar
              src="https://cdn-icons-png.flaticon.com/512/25/25231.png"
              size="2xs"
            />
          </template>
        </UButton>

      </div>
      
    </div>

    <div style="margin-top: 500px;margin-bottom: 200px;margin-left: 200px;">
      <h1 align="left" class="h1-title" style="font-size: 60px;width: auto;">Projects</h1>
      <p style="font-size: 20px;width: 500px;">This is my projects</p>
      <div style="display: flex;margin-top: 100px;margin-left: 200px;">
        
        <UCarousel
          style="width: 600px;height: 350px;"
          ref="carouselRef"
          v-slot="{ item }"
          :items="items"
          :ui="{ item: 'basis-full' }"
          class="rounded-lg overflow-hidden"
          indicators
        >
          <img :src="item" class="w-full" draggable="false">
        </UCarousel>

      </div>
      
    </div>
</template>

<style scoped>
* {
  font-family: Roboto, sans-serif;
}

.h1-title{
  background-image: linear-gradient(to right, red, yellow, green); /* Degradado de colores */
  -webkit-background-clip: text; /* Clip de fondo al texto (WebKit/Blink) */
  background-clip: text; /* Clip de fondo al texto */
  color: transparent; /* Oculta el color del texto */
  transition-duration: 1s;
}

.h1-title:hover{
  background-image: linear-gradient(to right, yellow, green, red); /* Degradado de colores */
  -webkit-background-clip: text; /* Clip de fondo al texto (WebKit/Blink) */
  background-clip: text; /* Clip de fondo al texto */
  color: transparent; /* Oculta el color del texto */
  transition-duration: 1s;
}

</style>

<script setup lang="ts">
const items = [
  'https://picsum.photos/1920/1080?random=1',
  'https://picsum.photos/1920/1080?random=2',
  'https://picsum.photos/1920/1080?random=3',
  'https://picsum.photos/1920/1080?random=4',
  'https://picsum.photos/1920/1080?random=5',
  'https://picsum.photos/1920/1080?random=6'
]

const carouselRef = ref()

onMounted(() => {
  setInterval(() => {
    if (!carouselRef.value) return

    if (carouselRef.value.page === carouselRef.value.pages) {
      return carouselRef.value.select(0)
    }

    carouselRef.value.next()
  }, 3000)
})
</script>
