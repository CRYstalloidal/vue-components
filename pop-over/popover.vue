<template>
    <div class="pop" @click.stop="" :style="{left:left+'px',top:top+'px','font-size':font_size+'em'}">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "popOver",
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
        font-size: 0.9em;
        position: absolute;
        /*top:-25px;*/
        /*left: 30px;*/
        width:300px;
        padding:8px;
        background-color: #FFFFFF;
        border: #cccccc solid 1px;
        border-radius: 3px;
    }
    .pop:before{
        box-sizing: content-box;
        width: 0px;
        height: 0px;
        position: absolute;
        top: 23px;;
        left: -16px;
        padding:0;
        border-right: 8px solid #FFFFFF;
        border-top:8px solid transparent;
        border-bottom: 8px solid transparent;
        border-left:8px solid transparent;
        display: block;
        content:'';
        z-index: 12;
    }
    .pop:after{
        box-sizing: content-box;
        width: 0px;
        height: 0px;
        position: absolute;
        top: 22px;;
        left: -18px;
        padding:0;
        border-right: 9px solid #cccccc;
        border-top:9px solid transparent;
        border-bottom:9px solid transparent;
        border-left:9px solid transparent;
        display: block;
        content:'';
        z-index:10
    }
</style>
