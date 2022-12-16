<template>
  <div class="inner-bg-img">
    <div class="intro-section per-section" id="Home">
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
                <img :src="icon.links && isSocMed == i ? icon.active : icon.icon" :alt="icon.title" class="icon">
                <a v-if="icon.links" :href="icon.links" class="emails" target="_blank" :class="isSocMed == i ? 'active' : ''">{{icon.email}}</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="about-section per-section" id="About">
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

    <div class="skills-section per-section" id="Skills">
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

    <div class="works-section per-section" id="Works">
      <div class="container">
        <h2 class="title-ov">WORKS</h2>
        <div class="tab-navs">
          <div class="tab" v-for="(tab, i) in tabs" :key="i">
            <p :class="isActive == i ? 'active':''" @click="openTab(i)">{{tab.nav}}</p>
          </div>
        </div>
        <div class="tab-info" >
          <div class="proj-list" v-for="(tab, i) in tabs" :key="i" :class="isActive == i ? 'active':''">
            <div v-for="(img, i) in tab.images" :key="i" class="img-grids">
              <img :src="img.img" alt="" @click="modal(img.img , 'img')" v-if="tab.tag == '0'">
              <video width="360" height="360" muted v-else @click="modal(img.img , 'vid')">
                <source :src="img.img" type="video/mp4">
              </video>
            </div>
          </div>
        </div>
      </div>
    </div>
    <modal name="popup" width="1200px" height="90%" :adaptive="true" :maxHeight="auto" class="mpop-img">
       <div class="popup-img">
        <img :src="popImg" v-if="types == 'img'">
        <video width="1200px" height="100%" controls v-else>
          <source :src="popImg" type="video/mp4">
        </video>
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
          tag: '0',
          images:[
            {
              img: '/images/yes.png',
              full: '/images/big1.png'
            },
            {
              img: '/images/yes2.png',
              full: '/images/big3.png'
            },
            {
              img: '/images/yes3.png',
              full: '/images/big2.png'
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
          tag: '0',
          images:[
            {
              img: '/images/Introducing-Khephren-staking-platform.jpg',
              full: '/images/Introducing-Khephren-staking-platform.jpg'
            },
            {
              img: '/images/Khephren-launchpad-launch-update.jpg',
              full: '/images/Khephren-launchpad-launch-update.jpg'
            },
            {
              img: '/images/OKC-is-now-live-on-kprnPAD (1).jpg',
              full: '/images/OKC-is-now-live-on-kprnPAD (1).jpg'
            },
            {
              img: '/images/Private-sale-launch (1).jpg',
              full: '/images/Private-sale-launch (1).jpg'
            },
            {
              img: '/images/Twitter-Giveaway-Winners.jpg',
              full: '/images/Twitter-Giveaway-Winners.jpg'
            },
          ]
        },
        {
          nav: 'Website',
          tag: '0',
          images:[
            {
              img: '/images/ABTI Web.png',
              full: '/images/ABTI Web.png'
            },
            {
              img: '/images/E-kaon.png',
              full: '/images/E-kaon.png'
            },
            {
              img: '/images/Mediation.jpg',
              full: '/images/Mediation.jpg'
            },
            {
              img: '/images/own Restaurant resto design.png',
              full: '/images/own Restaurant resto design.png'
            },
            {
              img: '/images/Ronach.png',
              full: '/images/Ronach.png'
            },
          ]
        },
        {
          nav: 'Mobile',
          tag: '0',
          images:[
            {
              img: '/images/2.png',
              full: '/images/2.png'
            }
          ]
        },
        {
          nav: 'Video Editing',
          tag: '1',
          images:[
            {
              img: '/images/10 Brocante video Ads.mp4',
              full: '/images/10 Brocante video Ads.mp4'
            },
            {
              img: '/images/Alsyone _ Yezh Animation Reveal!.mp4',
              full: '/images/Alsyone _ Yezh Animation Reveal!.mp4'
            },
            {
              img: '/images/update.mp4',
              full: '/images/update.mp4'
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
          icon: '/images/email_blue.svg',
          links: 'https://mail.google.com/mail/u/0/#inbox?compose=new',
          active: '/images/email.png',
        },
        {
          title: 'behance',
          email: 'https://www.behance.net/gvisionld',
          icon: '/images/Be.png',
          links: 'https://www.behance.net/gvisionld',
          active: '/images/behance_ac.svg'
        },
        {
          title: 'dribble',
          email: 'https://dribbble.com/Vision-LD',
          icon: '/images/dribble.png',
          links: 'https://dribbble.com/Vision-LD',
          active: '/images/dribbble_ac.svg'
        },
        {
          title: 'fb',
          email: '',
          icon: '/images/fb.png',
          links: '',
          active: '/images/facebook_ac.svg'
        },
      ],
      showSocMed: false,
      isSocMed: '',
      types:'',
    }
  },
  methods:{
    openTab(val){
      this.isActive = val
    },
    modal(val, type){
      this.types = type
      this.popImg = val
      console.log(this.types)
      this.$modal.show('popup')
    },
    showingSocMed(val){
      this.isSocMed = val
    }
  },
}
</script>
