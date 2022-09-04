<template>
    <transition :name="direction">
        <div v-show="visibleSlide === index" class="carousel-slide">
            <slot></slot>
        </div>
    </transition>
  </template>
  
  <script>
  export default {
    name:"CarouselSlide",
    props:['visibleSlide','index', 'direction'],
      data(){
          return{
  
          }
      }
  }
  </script>
  
  <style>
    .carousel-slide{
        position:absolute;
        top:0;
        left:0;
        right:0;
        bottom:0;
    }
    .left-enter-active{
        animation:leftInAnimation .5s ease-in-out;
    }
    .left-leave-active{
        animation:leftOutAnimation .5s ease-in-out;
    }
    @keyframes leftInAnimation {
        from{
            opacity:0.7;
            transform: translateX(100%)
        }
        to{
            opacity:1;
            transform: translateX(0)
        }
    }
    @keyframes leftOutAnimation {
        from{
            opacity:0.7;
            transform: translateX(0)
        }
        to{
            opacity:1;
            transform: translateX(-100%)
        }
    }
    .right-enter-active{
        animation:rightInAnimation .5s ease-in-out;
    }
    .right-leave-active{
        animation:rightOutAnimation .5s ease-in-out;
    }
    @keyframes rightInAnimation {
        from{
            opacity:0.7;
            transform: translateX(-100%)
        }
        to{
            opacity:1;
            transform: translateX(0)
        }
    }
    @keyframes rightOutAnimation {
        from{
            opacity:0.7;
            transform: translateX(0)
        }
        to{
            opacity:1;
            transform: translateX(100%)
        }
    }

  </style>