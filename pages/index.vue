<template>
  <div class="inner-bg-img">
    <div class="intro-section">
      <div class="container">
        <div class="left-intro-con">
          <div class="intro">
            <span>Hello, I’m</span><br/>
            <h1>
              CRISTINA
            </h1>
            <p>I am a Graphic Designer, I love making a simple & classy touch website design but my first priority will be your satisfaction & I love what I do.</p>
          </div>
          <div class="social-contact">
            <div class="sc-links">
              <div class="social-wrapper" v-for="(icon, i) in socialLinks" :key="i" @mouseenter="showingSocMed(i)">
                <img :src="icon.icon" :alt="icon.title" class="icon">
                <a href="#" class="emails" target="_blank" :class="isSocMed == i ? 'active' : ''">{{icon.email}}</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="about-section">
      <div class="container">
        <h2 class="title-ov">ABOUT ME</h2>
        <div class="about-descs">
          <div class="left-text">
            <p>I am passionate about every work that I'm in, with more than 2 years as a Graphic Designer full time experienced in the company I still enjoy every step of design process.</p>

            <p>In this industry I specialize in <b>Web Designing, Mobile Apps, Logo, Posters or social media banner</b> and a <b>simple animation/Video editing</b> as a profession not only to fulfill my needs but it has been my passion since 2018 and here using digital tools I can be creative and feel so awesome to do every line or shape that I made.</p>
          </div>
          <div class="right-text">
            <p>
              My goal as a designer is to provide creative, simple but classy, and thoughtful, but my first priority will be your satisfaction and opinion.
            </p>
            <p>
              I’m a Filipino, I am confident at my work. I can accomplish the goal of a quality result.
              I love singing and sports and also I like watching videos that very creative like hand writing/drawing specially related on Designs.
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="skills-section">
      <div class="container">
        <h2 class="title-ov">Skills</h2>
        <div class="skills-list">
          <div class="skill-item">
            <p>Adobe Photoshop <span>85%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
          <div class="skill-item">
            <p>Adobe XD <span>85%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
          <div class="skill-item">
            <p>Adobe Illustrator <span>85%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
          <div class="skill-item">
            <p>Figma <span>85%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
          <div class="skill-item">
            <p>Adobe After Effects <span>75%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
          <div class="skill-item">
            <p> Canva <span>80%</span></p>
            <div class="progress-bar-wrapper">
              <div class="prog-bar"></div>
            </div>
          </div>
        </div>
        <div class="skills-icons">
          <div class="skill-list" v-for="(skill, i) in skills" :key="i">
            <img :src="skill.img">
          </div>
        </div>
      </div>
    </div>

    <div class="works-section">
      <div class="container">
        <h2 class="title-ov">WORKS</h2>
        <div class="tab-navs">
          <div class="tab" v-for="(tab, i) in tabs" :key="i">
            <p :class="isActive == i ? 'active':''" @click="openTab(i)">{{tab.nav}}</p>
          </div>
        </div>
        <div class="tab-info" >
          <div class="proj-list" v-for="(tab, i) in tabs" :key="i" :class="isActive == i ? 'active':''">
            <div v-for="(img, i) in tab.images" :key="i">
              <img :src="img.img" alt="" @click="modal(img)">
            </div>
          </div>
        </div>
      </div>
    </div>
    <modal name="popup" width="1200px" height="600px" :adaptive="true">
       <div class="popup-img">
        <img :src="popImg.full">
       </div>
    </modal>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  layouts: "default",
  data(){
    return{
      skills: [
        {
          img: '/images/Vector.png'
        },
        {
          img: '/images/Group 206.svg'
        },
        {
          img: '/images/Component 1.svg'
        },
        {
          img: '/images/Group 207.svg'
        },
        {
          img: '/images/Group 228.svg'
        },
        {
          img: '/images/Group 209.svg'
        },
      ],
      tabs:[
        {
          nav: 'Logo',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big2.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes4.png',
              full: '/images/big4.png'
            },
            {
              img: '/images/yes5.png',
              full: '/images/big5.png'
            },
          ]
        },
        {
          nav: 'Poster/Banner',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big2.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes4.png',
              full: '/images/big4.png'
            },
            {
              img: '/images/yes5.png',
              full: '/images/big5.png'
            },
          ]
        },
        {
          nav: 'Website',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big2.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes4.png',
              full: '/images/big4.png'
            },
            {
              img: '/images/yes5.png',
              full: '/images/big5.png'
            },
          ]
        },
        {
          nav: 'Animation',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big2.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes4.png',
              full: '/images/big4.png'
            },
            {
              img: '/images/yes5.png',
              full: '/images/big5.png'
            },
          ]
        },
        {
          nav: 'Video Editing',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big12.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes4.png',
              full: '/images/big4.png'
            },
            {
              img: '/images/yes5.png',
              full: '/images/big5.png'
            },
          ]
        },
      ],
      isActive: '',
      popImg:{},
      socialLinks:[
        {
          title: 'gmail',
          email: 'gvisionld@gmail.com',
          icon: '/images/email.png'
        },
        {
          title: 'behance',
          email: 'gvisionld@gmail.com',
          icon: '/images/Be.png'
        },
        {
          title: 'dribble',
          email: 'gvisionld@gmail.com',
          icon: '/images/dribble.png'
        },
        {
          title: 'fb',
          email: 'gvisionld@gmail.com',
          icon: '/images/fb.png'
        },
      ],
      showSocMed: false,
      isSocMed: '',
    }
  },
  methods:{
    openTab(val){
      this.isActive = val
    },
    modal(val){
      this.popImg = val
      this.$modal.show('popup')
    },
    showingSocMed(val){
      this.isSocMed = val
    }
  },
}
</script>
