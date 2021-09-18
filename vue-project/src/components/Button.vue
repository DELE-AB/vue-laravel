<template>
    <button :style="{background:color}" class="btn" @click="onClick" >{{text}}</button>
</template>

<script>
export default {
    name:'Button',
    data() {
        return {
            clickCount: 0
        }
    },
    props:{
        text:String,
        color:String,
    },
    methods:{
        onClick(){
            this.clickCount++;
            if(this.clickCount == 2) {
                this.$emit('btn-click');
                this.clickCount = 0;
            }
        }
    }
}
</script>