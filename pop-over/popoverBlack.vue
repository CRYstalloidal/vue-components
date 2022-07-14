<template>
    <div class="pop" @click.stop="" :style="{left:left+'px',top:top+'px','font-size':font_size+'em'}">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "popOverBlack",
        props:{
            left:{
                default:0,
                type:Number
            },
            top:{
                default:0,
                type:Number
            },
            font_size:{
                default:1,
                type:Number
            }
        }
    }
</script>

<style scoped>
    .pop{
        font-size: 1em;
        position: absolute;
        color: white;
        /*top:-25px;*/
        /*left: 30px;*/
        width:300px;
        padding:8px;
        background-color: #4d4d4d;
        border: #cccccc solid 1px;
        border-radius: 3px;
    }
    .pop:after{
        box-sizing: content-box;
        width: 0px;
        height: 0px;
        position: absolute;
        top: 22px;;
        left: -18px;
        padding:0;
        border-right: 9px solid #4d4d4d;
        border-top:9px solid transparent;
        border-bottom:9px solid transparent;
        border-left:9px solid transparent;
        display: block;
        content:'';
        z-index:10
    }
</style>
