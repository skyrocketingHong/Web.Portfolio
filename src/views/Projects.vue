<template>
  <div class="container">
    <h1>Projects</h1>
    <p>Projects I participated in and/or developed.</p>

    <GitHubCard
      title="🤖 Bot.QQ"
      link="https://github.com/skyrocketingHong/Bot.QQ"
      :info="botQQAxios"
      :loading="loading"
    >
      <p>
        A QQ bot based on mirai. I developed some functions on it all by myself.
        <br>
        Click <a href="https://bot.skyrocketing.ninja/">here</a> for more infomations.
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
      botQQAxios: {
        stargazers_count: 0,
        forks_count: 0,
      }
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const botQQAxios = this.axios.get(`${githubApiUrl}/skyrocketingHong/Bot.QQ`)
    this.axios
      .all([botQQAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.botQQAxios = resp[0].data
        }),
      )
      .catch(err => {
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

</style>
