<template>
  <div class="container">
    <h1>Social</h1>
    <p>Some of my followers.</p>

    <div class="col-container">
      <div class="row-container">
        <statCard
          statTitle="Jike"
          :followers="jike.data"
          suffix="followers"
          icon="jike.png"
          :loading="jike.loading"
          link="https://m.okjike.com/users/0cdff532-44f1-4109-bfba-7da3debef5d5/"
        />
        <statCard
          statTitle="Zhihu"
          :followers="zhihu.data"
          suffix="followers"
          icon="zhihu.png"
          :loading="zhihu.loading"
          link="https://www.zhihu.com/people/skyrocketHong/"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="Twitter"
          :followers="twitter.data"
          suffix="followers"
          icon="twitter.png"
          :loading="twitter.loading"
          link="https://twitter.com/skyrocketinHong/"
        />
        <statCard
          statTitle="GitHub"
          :followers="github.data"
          suffix="followers"
          icon="github.png"
          :loading="github.loading"
          link="https://github.com/skyrocketingHong/"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="Weibo"
          :followers="weibo.data"
          suffix="fans"
          icon="weibo.png"
          :loading="weibo.loading"
          link="https://www.weibo.com/2947616165/"
        />
        <statCard
          statTitle="Steam Games"
          :followers="steamGames.data"
          suffix="games"
          icon="steam.png"
          :loading="steamGames.loading"
          link="https://steamcommunity.com/id/skyrocketingHong/"
        />
      </div>
    </div>

    <p id="substats-footer">
      * Follower statistics powered by:
      <a href="https://api.spencerwoo.com/substats">Substats</a>.
    </p>
  </div>
</template>

<script>
import statCard from '@/components/StatCard.vue'

export default {
  components: {
    statCard,
  },
  data() {
    return {
      jike: { data: 0, loading: true },
      zhihu: { data: 0, loading: true },
      twitter: { data: 0, loading: true },
      github: { data: 0, loading: true },
      weibo: { data: 0, loading: true },
      steamGames: { data: 0, loading: true },
    }
  },
  mounted() {
    const apiUrl = 'https://api.spencerwoo.com/substats'

    const jikeAxios = this.axios.get(`${apiUrl}/?source=jikeFollower&queryKey=0cdff532-44f1-4109-bfba-7da3debef5d5`)
    const zhihuAxios = this.axios.get(`${apiUrl}/?source=zhihu&queryKey=skyrocketHong`)
    const weiboAxios = this.axios.get(`${apiUrl}/?source=weibo&queryKey=2947616165`)
    const twitterAxios = this.axios.get(`${apiUrl}/?source=twitter&queryKey=skyrocketinHong`)
    const githubAxios = this.axios.get(`${apiUrl}/?source=github&queryKey=skyrocketingHong`)
    const steamGamesAxios = this.axios.get(`${apiUrl}/?source=steamGames&queryKey=76561198421901744`)

    jikeAxios.then((r) => {
      this.jike = { data: r.data.data.totalSubs, loading: false }
    })
    zhihuAxios.then((r) => {
      this.zhihu = { data: r.data.data.totalSubs, loading: false }
    })
    weiboAxios.then((r) => {
      this.weibo = { data: r.data.data.totalSubs, loading: false }
    })
    twitterAxios.then((r) => {
      this.twitter = { data: r.data.data.totalSubs, loading: false }
    })
    githubAxios.then((r) => {
      this.github = { data: r.data.data.totalSubs, loading: false }
    })
    steamGamesAxios.then((r) => {
      this.steamGames = { data: r.data.data.totalSubs, loading: false }
    })
  },
}
</script>

<style lang="css" scoped>
.col-container {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: stretch;
  align-content: center;
}

.row-container {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
  align-content: stretch;
  margin: 15px 0px;
}

.row-container .statCard:last-child {
  margin-left: 30px;
}

.row-container .statCard {
  flex: 1;
}

@media screen and (max-width: 760px) {
  .row-container {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: center;
  }

  .row-container .statCard:last-child {
    margin-left: 0px;
    margin-top: 30px;
  }
}

#substats-footer {
  color: #666666;
  text-align: left;
}
</style>
