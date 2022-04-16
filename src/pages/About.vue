<template>
  <Layout>
    <!-- Page Header-->
    <header class="masthead" style="background-image: url('/img/about-bg.jpg')">
        <div class="container position-relative px-4 px-lg-5">
            <div class="row gx-4 gx-lg-5 justify-content-center">
                <div class="col-md-10 col-lg-8 col-xl-7">
                    <div class="page-heading">
                        <h1>About Me</h1>
                        <span class="subheading">{{ about.sign }}</span>
                    </div>
                </div>
            </div>
        </div>
    </header>
    <!-- Main Content-->
    <main class="mb-4">
        <div class="container px-4 px-lg-5">
            <div class="row gx-4 gx-lg-5 justify-content-center">
                <div class="col-md-10 col-lg-8 col-xl-7">
                    <p>{{ about.introduction }}</p>
                    <p>{{ about.introduction2 }}</p>
                    <p>{{ about.introduction3 }}</p>
                </div>
            </div>
        </div>
    </main>
  </Layout>
</template>

<page-query>
query {
  about: allStrapiAbout {
      edges {
        node {
          sign
          introduction
          introduction2
          introduction3
        }
      }
    }
}
</page-query>

<script>
export default {
  name: 'AboutPage',
  metaInfo: {
    title: 'About us'
  },
  computed: {
    about () {
      return this.$page.about.edges[0].node
    }
  }
}
</script>
