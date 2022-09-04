<template>
  <div id="app">
    <h2>{{title}}</h2>
    <h3>{{subtitle}}</h3>
    <!-- <CarouselContainer
      @next="next" @prev="prev"
    > -->
    <div  class="carousel">
      <!-- <slot></slot> -->
      <button @click="next" class="next">Next</button>
      <button @click="prev" class="prev">Prev</button>

        <CarouselSlide v-for="(testemunho, index) in testemunhos" :key="testemunho" :index="index" 
        :visibleSlide="visibleSlide"
        :direction="direction"
        >
          <img :src="slides[index]" />
          <p :index="index">{{testemunhos[index]}}</p>
          <p :index="index">{{text[index]}}</p>
        </CarouselSlide>
    <!-- </CarouselContainer> -->
  </div>
  </div>
</template>

<script>
// import CarouselContainer from './components/CarouselContainer.vue';
import CarouselSlide from './components/CarouselSlide.vue';


export default {
  name: 'App',
  data(){
    return{
      slides: [
        'https://picsum.photos/id/237/600/300',
        'https://picsum.photos/id/238/600/300',
        'https://picsum.photos/id/239/600/300',
        'https://picsum.photos/id/26/600/300',
        'https://picsum.photos/id/235/600/300',
      ],
      title:'TITLE HERE',
      testemunhos: [
        '111Lorem ipsum dolor sit, amet consectetur adipisicing elit. Earum repellat sit quidem consectetur commodi, corrupti placeat deleniti possimus ad libero nemo nostrum ipsam ea vero magnam assumenda, molestiae hic fugit.',
        '222Lorem ipsum dolor sit, amet consectetur adipisicing elit. Earum repellat sit quidem consectetur commodi, corrupti placeat deleniti possimus ad libero nemo nostrum ipsam ea vero magnam assumenda, molestiae hic fugit.',
        '3333Lorem ipsum dolor sit, amet consectetur adipisicing elit. Earum repellat sit quidem consectetur commodi, corrupti placeat deleniti possimus ad libero nemo nostrum ipsam ea vero magnam assumenda, molestiae hic fugit.',
        '4444Lorem ipsum dolor sit, amet consectetur adipisicing elit. Earum repellat sit quidem consectetur commodi, corrupti placeat deleniti possimus ad libero nemo nostrum ipsam ea vero magnam assumenda, molestiae hic fugit.',
        '5555Lorem ipsum dolor sit, amet consectetur adipisicing elit. Earum repellat sit quidem consectetur commodi, corrupti placeat deleniti possimus ad libero nemo nostrum ipsam ea vero magnam assumenda, molestiae hic fugit.',
      ],
      subtitle: 'Subtitle 222222',
      text:[
        'lorem  lorem lorem 1111111',
        'lorem  lorem lorem 2222222222222',
        'lorem  lorem lorem 3333333333',
        'lorem  lorem lorem 444444444',
        'lorem  lorem lorem 555555555555',
      ],
      visibleSlide: 0,
      direction: 'left',
    }
  },
  computed:{
    slidesLen(){
      return this.slides.length;
    }
  },
  methods:{
    next(){
      if(this.visibleSlide >= this.slidesLen - 1){
        this.visibleSlide = 0;
      }else{
        this.visibleSlide++;
      }
      this.direction = "left"
    },
    prev(){
      if(this.visibleSlide <= 0){
        this.visibleSlide = this.slidesLen - 1;
      }else{
        this.visibleSlide--;
      }
      this.direction = "right"
    },
  },
  components: {
    // CarouselContainer,
    CarouselSlide
  }
}
</script>

<style>
#app {
  display:flex;
  justify-content: center;
  align-items: center;
  border:2px solid green;
  flex-direction:column;
  
}
.carousel{
  position:relative;
  width:600px;
  min-height:450px;
  overflow: hidden;
  border:2px solid red;
}
button{
  position: absolute;
  height: 40px;
  width: 50px;
  top: calc(50% - 20px);
  background: black;
  border:none;
  color:white;
  z-index:10;
}
button:focus, button:hover{
  outline:none;
  cursor:pointer;
  background: lightblue;
}
.next{
  right:0;
}
.prev{
  left:0;
}
</style>
