<template>
<<<<<<< HEAD
  
  <div class="w-1/2 flex flex-col h-auto gap-5 max-lg:w-full max-2xl:h-auto max-2xl:mt-20">
    <div class="h-auto">
      <h2 id="element" class=" h-full pb-2 selector opacity-100 text-6xl h-auto font-bold max-2xl:text-5xl max-2xl:flex max-2xl:justify-center max-2xl:items-center         max-md:text-4xl bg-gradient-to-r from-[#0067f4] to-[#DFE5F5] text-transparent bg-clip-text">{{ title }}</h2>
=======
  <div class="w-full h-container flex flex-col justify-center gap-20 items-start max-2xl:gap-10 max-2xl:h-eighy-vh">
    <div>
      <h1 id="element" class="selector text-8xl font-bold max-2xl:text-5xl max-md:text-4xl bg-gradient-to-r from-cyan-500 to-blue-500 text-transparent bg-clip-text">{{ title }}</h1>
asas

>>>>>>> site3

    </div>

    <span class="h-auto opacity-100 selector text-2xl max-2xl:text-base max-md:text-xl" ref="descrip">{{ description }}</span>
    <div class="selector opacity-100">
      <BtnRedirection :title="redirectiontitle" :redirection="redirection" :showarrow="showarrow" widthtext="w-16"/>
    </div>
    <div class="selector opacity-100">
      <BtnRedirection :title="redirectiontitle2" :redirection="redirection2" :showarrow="showarrow" widthtext="w-20"/>
    </div>



  </div>
  </div>
</div>

</template>
<script setup>

const props = defineProps({
  title: String,
  description: String,
  redirectiontitle: String,
  redirection: String,
  redirectiontitle2: String,
  redirection2: String,
  showarrow :String,
})


// const { $gsap } = useNuxtApp()
import { gsap } from 'gsap'
let tl = gsap.timeline()
const jsp = ref(props.description)

const heroAnimation = () => {


  
    tl.to('.selector ',
      {
       
        opacity: 1,
                 y: 0,
                duration: 1,
                stagger:0.1
       
      })
  




}

onMounted(() => {
  // titleHomeAnimation({element : '.selector'})
  heroAnimation()

})


</script>

<style scoped>
.selector{
  opacity: 0;
  transform: translateY(100px);
}
</style>