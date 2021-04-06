<template>
    <div>
        <button @click="isOpen = !isOpen">
            My Profile
        </button>

        <transition
            @before-enter="beforeEnter"
            @enter="enter"
            @leave="leave"
            :css="false"
        >
            <div v-if="isOpen"  class="drawer">
                <div>naser</div>
                <div>vue programmer</div>
                <div>30 years old</div>
            </div>
        </transition>
    </div>
</template>

<script>
    import Velocity from "velocity-animate"
    export default {
        name:"Drawer",
        data(){
            return{
                isOpen:false
            }
        },
        methods:{
            beforeEnter(el){
                el.style.opacity = 0
                el.style.width = "0em"
            },
            enter(el, done){
                Velocity(
                            el, 
                            {opacity:1, width:"12em"},
                            {duration: 1000, easing:"easeOutCubic", complete: done}
                        )
            },
            leave(el, done){
                Velocity(
                            el, 
                            {opacity:0, width:"0em"},
                            {duration: 500, easing:"easeInCubic", complete: done}
                        )
            },
        }
    }
</script>

<style scoped>
.drawer{
    background-color: #ccc;
    height: 100%;
    position: absolute;
    left: 0;
    bottom: 0;
    top: 0;
}
</style>