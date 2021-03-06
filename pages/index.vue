<template>
  <section class="content">
    <section class="hero is-medium card is-bold who-card">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Who is it for ?
          </h1>
          <p class="text-2xl font-semibold">
            Are you a <a class=" text-teal-300 hover:text-teal-500" href="http://notion.so/" target="_blank"> Notion </a> user ?
            Do you want to organize your notes with beautiful Icons ? This for you!
          </p>
        </div>
      </div>
    </section>
    <section id="how-to-use" class="hero card mt-10 card is-medium how-card is-bold">
      <div class="columns hero-body text-gray-900">
        <div class="column is-half container border-gray-300 border-r-2">
          <h1 class="title">
            How to use it ?
          </h1>
          <div class="text-2xl">
            <ol>
              <li>
                Go to
                <nuxt-link to="/icons">
                  Icons tab
                </nuxt-link>
              </li>
              <li>
                Type keywords in <code>Search box</code> to filter icons.
              </li>
              <li>
                You can customize color by clicking color swatch.
              </li>
              <li>
                If you use dark mode in Notion, you can toggle <code>Dark mode button</code> to see how it looks in dark mode.
              </li>
              <li>
                Click on the Icon to copy url to clipboard.
              </li>
              <li>
                Go to your Notion app, click on icon, go to Link tab and paste the copied url.
              </li>
              <li>
                Hit Enter. The icon will be updated.
              </li>
            </ol>
          </div>
        </div>
        <div class="column is-half">
          <h1>
            Watch Demo
          </h1>
          <div class="video-container">
            <iframe
              src="https://www.youtube.com/embed/otaWCicokTc"
              width="560"
              height="315"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            />
          </div>
        </div>
      </div>
    </section>
    <section class="hero card mt-10 card is-medium is-bold why-card">
      <div class="hero-body text-gray-900">
        <div class="container">
          <h1 class="title">
            Why use it ?
          </h1>
          <p class="text-2xl">
            Notions comes with only limited set of icons. We can get beautiful icons from many websites like
            <a class="text-teal-800 hover:text-teal-600" href="https://icons8.com/" target="_blank"> Icon8 </a> ,
            <a class="text-teal-800 hover:text-teal-600" href="https://www.flaticon.com/" target="_blank"> Flaticon </a> .
            But it is
            <a href="/about/#why-i-built" class="text-teal-900 hover:text-teal-700">
              painful
            </a>
            to add icons from those websites to notion notes.
          </p>
          <blockquote class="text-2xl">
            Now, You can easily add beautiful icons to your notes using Notion Icons.
          </blockquote>
        </div>
      </div>
    </section>
  </section>
</template>

<script lang="ts">

import { Component, Vue } from 'nuxt-property-decorator'
import VueScrollTo from 'vue-scrollto'
import { getCurrentPageUrl } from '../gallery/AppUtils'

@Component
export default class extends Vue {
  head () {
    return {
      titleTemplate: 'Home | %s',
      meta: [
        { name: 'og:url', content: getCurrentPageUrl('/') },
        { name: 'twitter:url', content: getCurrentPageUrl('/') }
      ]
    }
  }

  mounted () {
    if (this.$route.hash) {
      this.scrollToHash()
    }
  }

  scrollToHash () {
    const hash = this.$route.hash
    this.$nextTick(() => {
      VueScrollTo.scrollTo(hash, 0)
    })
  }
}

</script>

<style scoped>
  p, blockquote {
    font-family: KoHo,sans-serif;
  }

  blockquote {
    background-color: #E7F9EB;
    font-style: italic;
    font-weight: 600;
    border-left: 5px solid #374454;
  }

  h1 {
    color: #374454
  }

  .why-card {
    background-color: #E7F9EB;
  }

  .who-card {
    background-color: #374454;
    color: white;
  }

  .who-card h1 {
    color: white;
  }

  .how-card {
    background-color: #FAF7F0;
  }

  .how-card h1 {
    color: #EC2D2A;
  }

  .card {
    box-shadow: 0 2px 2px 0 rgba(34, 41, 47, 0.05), 0 8px 8px 0 rgba(34, 41, 47, 0.05);
  }

  .video-container {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
  }

.video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 95%;
    height: 95%;
    box-shadow: rgba(40, 40, 40, 0.15) 0px 20px 80px;
  }
</style>
