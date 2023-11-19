<script setup lang="ts">
 const team = [
  {name:'مهدی شمس'  , pic:'/photo_2023-04-12_11-45-13.jpg' , info:'وقفه ها در ESP32'},
  { name: 'سهیل سلیمی',  pic: '/PXL_20231115_072438741.MV.jpg', info: 'کنترلLED با  IoT' },
 { name: 'سپهر شیرازی',  pic: '/photo_2023-11-18_20-19-18.jpg', info: 'معرفی انواع و کاربرد های پین ها  درEsp32' },
     { name: 'محمد امین آقا کبیری',  pic: '/photo_2023-11-18_22-12-04.jpg' ,  info: 'esp32 در IoT' }
 ]
</script>

<template>
  <div class="cont">
    <div  class="grid grid-cols-2 gap-4 justify-items-center">
    <div class="flex flex-col card" v-for="(per, index) in team" :key="index">
           
                  <div class="flex flex-wrap justify-center">
    
             <img :src="per.pic" alt="..." class="shadow-lg rounded-full w-34 h-34 p-5" />
                  <h6 class="text-center text-white ">{{ per.name }}</h6>
                  <h6 class="text-slate-300 text-sm text-center">{{ per.info }}</h6>
              </div>
      </div>
    </div>
   
  </div>

</template>

<style scoped>
.cont {
    background: url(/Webp.net-resizeimage.jpg) no-repeat center center fixed; 
   height: 100%;

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.card{
    height: 230px;
    width: 230px;
    background-color: rgba(255, 255, 255, 0.06);
    -webkit-backdrop-filter: blur(20px);
            backdrop-filter: blur(20px);
    border-radius: 8px;
    -webkit-box-shadow: 20px 20px 22px rgba(0,0,0,0.2);
            box-shadow: 20px 20px 22px rgba(0,0,0,0.2);
}

</style>