<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="About Me"
      subtitle="Rafael Viana"
      image="/uploads/about-hero.jpg"
    ></site-hero>
    <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="content">
          <h2 class="section__title section__title--services">What I do</h2>
          <div class="services">
            <div class="service">
              <h3>Full Stack Developer</h3>
              <p>
                I have commercial experience in ReactJS and NodeJS applications.
                I have worked on the state management of a web portal on its
                transition to become biligual, leveraging several React-related
                technologies and i18n. As a Node/Express developer, I have
                contributed to a web-based school management system.
              </p>
            </div>
            <div class="service">
              <h3>Educator</h3>
              <p>
                I have worked as an instructor and tech mentor - assisting
                novice developers in achieving their dreams through technology,
                as well as teaching programming and computer science
                fundamentals on weekends, events, and evenings.
              </p>
            </div>
            <div class="service">
              <h3>Communicator</h3>
              <p>
                I have worked as Technical Support specializing in software
                troubleshooting and conflict resolution. I was awarded
                優秀コミュニケーター of my department due to the various
                positive reviews I had accumulated from customers. I also have
                in public speaking.
              </p>
            </div>
          </div>
        </div>
      </template>
    </main-section>
  </div>
</template>
<script>
export default {
  head() {
    return {
      title: `About | ${this.$siteConfig.siteName}`
    }
  }
}
</script>
