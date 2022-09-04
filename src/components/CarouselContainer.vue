<!-- <template>
  <div  class="carousel">
        <slot></slot>
        <button @click="next" class="next">Next</button>
        <button @click="prev" class="prev">Prev</button>
  </div>
</template>

<script>
export default {
    name: "CarouselContainer",
    data(){
        return{

        }
    },
    methods:{
        next(){
            this.$emit('next')
        },
        prev(){
            this.$emit('prev')
        },
    }
}
</script>

<style>
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
</style> -->