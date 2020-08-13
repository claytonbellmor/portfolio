<template>
  <div class="container">
    <h1>Projects</h1>
    <p>My front end development portfolio.</p>

    <GitHubCard
      title="🤩 Egypt Travel Brochure"
      link="https://www.claytonbellmor.com/project_one"
      :info="egyptInfo"
      :loading="loading"
    >
      <p>
        Inspired by
        <a href="https://dribbble.com/shots/7147835/attachments/152048?mode=media" target="_blank" alt="Dribbble"
          >Dribbble</a
        >
        for my first project. This brochure site used inline SVG, font replacements, and Vue.
      </p>
      <p>It uses multiple breakpoints, image source sets, and vanilla Javascript.</p>
      <p>
        This repository uses Github Actions to automatically upload to a web hosting server each time a commit is
        pushed, which is neat-o.
      </p>
      <div class="preview-container">
        <img src="./../assets/previews/project-one-preview.jpg" alt="Egypt Preview" />
      </div>
      <p>
        <a href="https://www.claytonbellmor.com/project_one" target="_blank"
          ><span class="title-font">🌎</span> Live Site Preview</a
        >.
      </p>
      <p>
        <a href="https://github.com/claytonbellmor/Go-To-Egpyt-Travel-Brochure" target="_blank"
          ><img class="title-font" src="./../assets/images/github.svg" /> Github Code</a
        >.
      </p>
    </GitHubCard>

    <GitHubCard
      title="🛸 Election Website"
      link="https://www.claytonbellmor.com/project_two"
      :info="electionInfo"
      :loading="loading"
    >
      <p>
        My second project had a mobile first approach rather than responsive design. It was inspired by a real campaign
        website, which I copied into Figma.
      </p>
      <p>
        Compared to my first project, this website was much easier to code and I had a lot of fun doing it. Bootstrap
        and the Less preprocessor were used.
      </p>
      <p>Automatic publishing with Github Actions.</p>
      <div class="preview-container">
        <img src="./../assets/previews/project-two-preview.jpg" alt="Egypt Preview" />
      </div>
      <p>
        <a href="https://www.claytonbellmor.com/project_two" target="_blank"
          ><span class="title-font">🌎</span> Live Site Preview</a
        >.
      </p>
      <p>
        <a href="https://github.com/claytonbellmor/election-campaign-website" target="_blank"
          ><img class="title-font" src="./../assets/images/github.svg" /> Github Code</a
        >.
      </p>
      <p>
        <a href="https://www.figma.com/file/1xEgGUedEUS0x7YrwhJG2c/Website-2?node-id=0%3A1" target="_blank"
          ><img class="title-font" src="./../assets/images/figma.svg" /> Figma Mockup</a
        >.
      </p>
    </GitHubCard>

    <GitHubCard
      title="🏁 Vuetify Car App"
      link="http://claytonbellmor.com/project_three/#/mycar"
      :info="carappInfo"
      :loading="loading"
    >
      <p>
        In my journey of learning front end develop, I've been bombarded by React tutorials and lessons. When I
        discovered Vue, I really preferred it. I wanted my third project to encompass Vue and APIs.
      </p>
      <p>
        I subscribed to Vue Mastery for a month and went through all the lessons. Vuetify seemed like cheating and I
        wanted to build an app based on the Material Design standard.
      </p>
      <p>
        This app is hosted privately.
      </p>
      <div class="preview-container">
        <img src="./../assets/previews/project-three-preview__garage.png" alt="Egypt Preview" />
        <img src="./../assets/previews/project-three-preview__car.jpg" alt="Egypt Preview" />
      </div>
      <p>
        <a href="http://claytonbellmor.com/project_three/#/mycar" target="_blank"
          ><span class="title-font">🌎</span> Live Site Preview</a
        >.
      </p>
      <p>
        <a href="https://github.com/claytonbellmor/mycarapp" target="_blank"
          ><img class="title-font" src="./../assets/images/github.svg" /> Github Code</a
        >.
      </p>
    </GitHubCard>
  </div>
</template>

<script>
import GitHubCard from '@/components/GitHubCard.vue'

export default {
  components: {
    GitHubCard,
  },
  data() {
    return {
      loading: true,
      egyptInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      electionInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      carappInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const egyptAxios = this.axios.get(`${githubApiUrl}/claytonbellmor/Go-To-Egpyt-Travel-Brochure`)
    const electionAxios = this.axios.get(`${githubApiUrl}/claytonbellmor/election-campaign-website`)
    const carappAxios = this.axios.get(`${githubApiUrl}/claytonbellmor/mycarapp`)

    this.axios
      .all([egyptAxios, electionAxios, carappAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.egyptInfo = resp[0].data
          this.electionInfo = resp[1].data
          this.carappInfo = resp[2].data
        }),
      )
      .catch((err) => {
        this.loading = false
        // eslint-disable-next-line no-console
        console.error(err)
      })
  },
}
</script>

<style scoped>
.container .github-project-card:not(:last-child) {
  margin-bottom: 40px;
}

p {
  line-height: 30px;
}

.preview-container {
  height: 300px;
  overflow-y: scroll;
  overflow-x: hidden;
  border-radius: 15px;
}

.preview-container img {
  width: 100%;
}

.title-font {
  width: 16px;
  height: 16px;
  margin-right: 4px;
}
</style>
