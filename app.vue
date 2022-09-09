<template>
  <div class=" collaborate-page-content">
    <h1 style="text-align: center; " class="text-5xl">
      Huzail Hassan
    </h1>



    <div style="text-align: center; " class="py-3">
      <h2>
        Who am I?
      </h2>
    </div>

    <div style="text-align: center; " class="text-xl">
      <p>
        I am a Full-Stack Software Engineer and hold a bachelors degree in Computer Science from California State Polytechnic University, Pomona.
        From a young age, I started creating websites, posters, and other designs for local companies and organizations. My skills progressively improved and through my years of experience in design and programming, I have produced many projects which I am proud to showcase.
        Below are some of the projects I would like to show you!
      </p>
    </div>

    <div style="text-align: center; " class="py-3">
      <h2>
        See my projects!
      </h2>
    </div>
    <Gallery></Gallery>
    <div style="text-align: center; " class="text-xl">
      <v-btn @click="openGithub" class="justify-center mr-2">See more on GitHub！</v-btn>
      <v-btn @click="openLinkedIn" class="justify-center"> Connect with me on LinkedIn</v-btn>

    </div>

  </div>
</template>

<style lang="scss">
.collaborate-page-content {
  max-width: 950px;
  margin: 2.5rem auto;
}
</style>
<script>
import Gallery from "./components/Gallery";
export default {
  components: {Gallery},
  methods: {
    openGithub() {
      window.open('https://github.com/huzailhassan/')
    },
    openLinkedIn() {
      window.open('https://www.linkedin.com/in/huzailhassan/')
    }
  }
}
</script>

<style>
body {
  background: linear-gradient(-45deg, #FED8B1, #FFCCCB, #ADD8E6, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  height: 100vh;
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

</style>
