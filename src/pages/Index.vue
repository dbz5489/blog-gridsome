<template>
  <layout>
    <!-- Page Header-->
    <header class="masthead" style="background-image: url('/img/home-bg.jpg')">
      <div class="container position-relative px-4 px-lg-5">
        <div class="row gx-4 gx-lg-5 justify-content-center">
          <div class="col-md-10 col-lg-8 col-xl-7">
            <div class="site-heading">
              <h1>我的博客</h1>
              <span class="subheading"
                >strapi版本更新不能通过插件连接了老师</span
              >
            </div>
          </div>
        </div>
      </div>
    </header>
    <!-- Main Content-->
    <div class="container px-4 px-lg-5">
      <div class="row gx-4 gx-lg-5 justify-content-center">
        <div class="col-md-10 col-lg-8 col-xl-7">
          <!-- Post preview-->
          <section
            v-for="(item, index) in $page.posts.edges"
            :key="item.node.id"
          >
            <div class="post-preview">
              <g-link :to="item.node.path">
                <h2 class="post-title">
                  {{ item.node.title }}
                </h2>
                <h3 class="post-subtitle">
                  Problems look mighty small from {{ index }} miles up
                </h3>
              </g-link>
              <p class="post-meta">
                Posted by
                <g-link>Start Bootstrap</g-link>
                date
              </p>
            </div>
            <!-- Divider-->
            <hr class="my-4" />
          </section>
        </div>
      </div>
    </div>
  </layout>
</template>
<page-query>
query{
  posts:allPost {
    edges {
      node {
        id
        title
        content
        path
      }
    }
  }
}

</page-query>
<script>
export default {
  name: "IndexPage",
  components: {},
  metaInfo: {
    title: "Hello, world!"
  }
};
</script>

<style></style>
