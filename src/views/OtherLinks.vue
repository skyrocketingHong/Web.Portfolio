<template>
  <div class="container">
    <h1>Other Links</h1>
    <p>Other Links.</p>

    <LinkCard
      title="skyrocketing's Blog"
      link="https://blog.skyrocketing.ninja/"
    >
      <p>
        Blog link. Build by Wordpress.
      </p>
    </LinkCard>
    <br>
    <LinkCard
      title="Domain Mail"
      link="https://domainmail.skyrocketing.ninja/"
    >
      <p>
        Domain mail link. Host by Ali Exmail.
      </p>
    </LinkCard>
    <br>
    <LinkCard
      title="Admin Page"
      link="https://admin.skyrocketing.ninja/"
    >
      <p>
        Admin page.
      </p>
    </LinkCard>

    <br>
    <LinkCard
      title="Adguard DNS"
      link="https://dns.skyrocketing.ninja/"
    >
      <p>
        Adguard DNS admin page.
      </p>
    </LinkCard>

  </div>
</template>

<script>
import LinkCard from '@/components/LinkCard.vue'

export default {
  components: {
    LinkCard,
  }
}
</script>

<style scoped>
.container .github-project-card:not(:last-child) {
  margin-bottom: 40px;
}

</style>
