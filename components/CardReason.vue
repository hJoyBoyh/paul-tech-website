<template>
    
<div class="w-full h-full flex max-lg:flex-col justify-between max-lg:justify-around items-center">
    <div class="flex flex-col w-full gap-20">
        <h2 class="text-4xl font-bold">{{$t('card_reason_title')}}</h2>
        <div class="flex flex-col gap-5">
        <p class="font bold text-2xl duration-300 hover:text-[#0067f4] cursor-pointer" :class="{'text-white': !isActive1, 'text-[#0067f4]': isActive1}"  @click="toggleClick(1)">{{$t('card_reason_sub_title_1')}}</p>
        <p class="font bold text-2xl  duration-300 hover:text-[#0067f4] cursor-pointer" :class="{'text-white': !isActive2, 'text-[#0067f4]': isActive2}"  @click="toggleClick(2)">{{$t('card_reason_sub_title_2')}}</p>
        <p class="font bold text-2xl  duration-300 hover:text-[#0067f4] cursor-pointer" :class="{'text-white': !isActive3, 'text-[#0067f4]': isActive3}"  @click="toggleClick(3)">{{$t('card_reason_sub_title_3')}}</p>
        </div>
      

    </div>
    <div class=" w-full flex flex-col gap-10 w-auto">
        <p class="text-3xl "  :class="[isActive1 == false ? cardOff : '', cardOn]" @click="toggleClick(1)" > {{ $t('card_reason_description_1') }}</p>
          <p class="text-3xl" :class="[isActive2 ==  false ? cardOff : '', cardOn]" @click="toggleClick(2)"  > {{ $t('card_reason_description_2') }}</p>
              <p class="text-3xl"  :class="[isActive3 ==  false ? cardOff : '', cardOn]" @click="toggleClick(3)" > {{ $t('card_reason_description_3') }}</p>
    </div>
</div>
</template>
<script setup>
const cardOn = ref('card-on')
const cardOff = ref('card-off')

const isActive1 = ref(true)
const isActive2 = ref(false)
const isActive3 = ref(false)

const toggleClick  = (e) =>{
    if(e==1){
        isActive1.value = true
        isActive2.value = false

        isActive3.value = false

        
    }
    if(e == 2){
        isActive1.value = false
        isActive2.value = true

        isActive3.value = false

    } if(e == 3){
        isActive1.value = false
        isActive2.value = false

        isActive3.value = true

    }
}

onMounted(() => {
    // toggleClick();
})
</script>
<style scoped>
.card-on{
    display: block;
}
.card-off{
    display: none;
}

.cursor-pointer:focus{
    

}
</style>