<template>
    <div class="wrap">
        <input type="number" v-model="childvalue">
        <input type="button"  class="up" @click="increase" />
        <input type="button"  class="down" @click="decrease" />
    </div>
</template>

<script>
    export default {
        name: "IntegerInput",
        props:{
            value:{
                default:0,
                type:Number
            }
        },
        methods:{
            increase(){
                this.childvalue++;
            },
            decrease(){
                if(Number(this.childvalue)>=2){
                    this.childvalue--;
                }
            }
        },
        data(){
            return{
                childvalue: this.value,
            }
        },
        watch: {
            value(newVal){
                this.childvalue = newVal;
            },
            childvalue(newVal){
                // console.log(newVal)
                this.$emit('valueChanged',newVal);
            }
        }
    }
</script>

<style scoped>
    .wrap{
        position: relative;
        display: inline-block;
    }
    input[type="number"]{
        border:1px solid gainsboro;
        width: 90px;
        height: 40px;
        border-radius: 5px;
        padding-left: 10px ;
    }
    input[type="number"]::-webkit-inner-spin-button,
    input[type="number"]::-webkit-outer-spin-button {
        height: auto;
        -webkit-appearance: none;
    }
    .up,.down{
        position: absolute;
        background-color: white;
        width: 29px;
        height: 19px;
        border: none;

        background-repeat: no-repeat;
        background-size: 15px 15px;
        background-position: 7.5px 2.5px;
        left: 60px;
    }
    .up{
        border-left:1px solid gainsboro;
        border-bottom:1px solid gainsboro;

        background-image: url("up.png");
        top: 1px;
        border-start-end-radius: 5px;
    }
    .down{
        border-left:1px solid gainsboro;
        border-top:1px solid gainsboro;

        background-image: url("down.png");
        top: 20px;
        border-end-end-radius: 5px;
    }
    .up:hover,.down:hover{
        background-color: gainsboro;
    }
</style>
