<template>
  <main>
    <div class="outer-wrapper">
      <div class="wrapper">
        <div class="section-welcome">
          <div class="welcome-text-namegroup">
            <div class="welcome-text-name">
              <p class="title welcome-ryan">Ryan</p>
              <p class="title welcome-vankriekinge">Vankriekinge</p>
            </div>
            <svg
              class="name-svg"
              viewBox="0 0 100 100"
              xmlns="http://www.w3.org/2000/svg"
              width="100%"
              height="100%"
            >
              <polygon points="50,10 0,75 500,75 500,10" fill="#57378B" />
            </svg>
          </div>
          <div class="welcome-text-career">
            <div class="welcome-text-jobtitle">
              <svg
                class="function-svg"
                viewBox="0 0 100 100"
                xmlns="http://www.w3.org/2000/svg"
                width="100%"
                height="100%"
              >
                <polygon points="-500,0 -500,35 20,35 0,0" fill="#57378B" />
              </svg>
              <p class="jobtitle">Portfolio</p>
            </div>
            <div class="welcome-text-skills"></div>
          </div>
        </div>
        <div class="section-about-me">
          <div class="about-me-description">
            <h2 class="title">About me</h2>
            <p>
              Ever since I was a child, I have been passionate about content creation and multimedia
              tools. When I was 9, I made my first edited videos and created blogs and websites for
              my classmates. Later, I managed various YouTube channels and learned to use graphic
              software to design my own logos, thumbnails, and video elements. Driven by this
              passion, I chose to study Multimedia and Creative Technology, where I further
              developed my skills. <br /><br />
              Alongside my studies, I've been working as a teacher for several years and organized
              activities for a youth organization. These experiences strengthened my communication
              and organizational skills and gave me a high sense of responsibility. I enjoy working
              in a team, but I am also able to work independently and take initiative.
              <br /><br />
              I constantly seek ways to further develop my creativity and technical skills. My goal
              is to create innovative and impactful content and tools that resonate with the right
              audience. With my drive and eagerness to learn, I am convinced that I can be a
              valuable addition to any team.
            </p>
            <button class="button-small">More about me</button>
          </div>
          <div class="about-me-image-group">
            <div class="about-me-image-container">
              <img src="../assets/img/ryanvankriekinge.png" />
            </div>
            <div class="about-me-shape"></div>
          </div>
        </div>
        <div style="height: 100vh"></div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const tl = gsap.timeline()
  // initial animation welcome section
  tl.from('.name-svg', {
    x: '100vw',
    duration: 1.5,
    ease: 'power3.out',
  })
    .to({}, {})
    .from('.welcome-text-name', {
      x: '20vw',
      opacity: 0,
      duration: 1.5,
      ease: 'power3.out',
    })
    .to({}, { duration: 0.5 })
    .from(['.function-svg', '.jobtitle'], {
      x: '-100vw',
      opacity: 0,
      duration: 1.5,
      ease: 'power3.out',
      stagger: 0,
    })

  // scroll triggered animations

  // welcome section
  gsap
    .timeline({
      scrollTrigger: {
        trigger: '.section-welcome',
        start: 'bottom 80%',
        end: 'bottom top',
        scrub: 0.5,
      },
    })
    .to('.welcome-text-namegroup', {
      x: '100vw',
      opacity: 0,
      duration: 1,
      ease: 'power3.out',
    })
    .to(
      '.welcome-text-career',
      {
        x: '-100vw',
        opacity: 0,
        duration: 1,
        ease: 'power3.out',
      },
      0.2,
    )

  //about-me-section : enter animation
  gsap
    .timeline({
      scrollTrigger: {
        trigger: '.section-about-me',
        start: 'top bottom',
        end: 'top 20%',
        scrub: 0.5,
      },
    })
    .from(
      '.about-me-description > *',
      {
        x: '-100vw',
        opacity: 0,
        duration: 1,
        ease: 'power3.out',
        stagger: 0.2,
      },
      0,
    )
    .from(
      '.about-me-image-group > *',
      {
        x: '100vw',
        opacity: 0,
        duration: 1,
        ease: 'power3.out',
        stagger: 0.4,
      },
      0,
    )

  // about-me-section : exit animation

  gsap
    .timeline({
      scrollTrigger: {
        trigger: '.section-about-me',
        start: 'bottom 80%',
        end: 'bottom-=20% top',
        scrub: 1,
      },
    })
    .to(
      '.about-me-description > *',
      {
        x: '-100vw',
        opacity: 0,
        duration: 1,
        ease: 'power3.in',
        stagger: 0.2,
      },
      0,
    )
    .to(
      '.about-me-image-group > *',
      {
        x: '100vw',
        opacity: 0,
        duration: 1,
        ease: 'power3.in',
        stagger: 0.4,
      },
      0,
    )
})
</script>
