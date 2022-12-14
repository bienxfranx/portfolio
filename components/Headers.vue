<template>
    <div class="outer-nav" :class="{ active: displayTop}">
        <div class="container-hf navigation">
            <div class="logo">
                <img src="/images/logo.png" alt="logo">
            </div>
            <div class="nav-items">
                <!-- <a href="#" class="nav-item active">Home</a>
                <a href="#" class="nav-item">About</a>
                <a href="#" class="nav-item">Skills</a>
                <a href="#" class="nav-item">Works</a>
                <a href="#" class="nav-item">Contact</a> -->
                <div :class="isNavActive == i ? 'active' : ''" class="nav-item" v-for="(nav, i) in navs" :key="i" @click="getNav(i, nav.id)">
                    {{nav.tab}}
                </div>
            </div>
            <div class="talk-btn">
                <a href="https://mail.google.com/mail/u/0/#inbox?compose=new" target="_blank">Let’s Talk!</a>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            navs:[
                {
                    tab: 'Home',
                    id: 'Home',
                },
                {
                    tab: 'About',
                    id: 'About'
                },
                {
                    tab: 'Skills',
                    id: 'Skills'
                },
                {
                    tab: 'Works',
                    id: 'Works'
                },
                {
                    tab: 'Contact',
                    id: 'Contact'
                }
            ],
            isNavActive: false,
            displayTop: false
        }
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll)
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll)
    },
    methods:{
        getNav(val, id){
            this.isNavActive = val
            document.getElementById(id).scrollIntoView();
        },
        onScroll(e) {
            this.windowTop = window.top.scrollY
                if(this.windowTop >= 25){
                    this.displayTop = true;
                }else{
                    this.displayTop = false;
                }
            },
    }
}
</script>