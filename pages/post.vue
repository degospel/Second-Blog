<template>
  <div class="post-page">

    <!-- NAVBAR -->
    <nav class="navbar">
      <div class="title">
          <h2>
            Fashion Blog
          </h2>
      </div>

      <div class="categories">
          <ul>
              <li>
                  <NuxtLink to="/" class="blogdiv"><i class='bx bx-left-arrow'></i>Back</NuxtLink>
              </li>
          </ul>
      </div>
    </nav>

    <h2>Latest Post</h2>
    <div class="articles cards">
        <div class="article card card1" v-for="article of articles" :key="article">
            <nuxt-link :to="{ name: 'slug', params: { slug: article.slug } }" class="link">
              <div class="container">
                  <img :src="require(`~/assets/img/${article.img}`)" alt="">
              </div>
              <div class="details">
                  <h3>{{ article.title }}</h3>
                  <p>{{ article.description }}</p>
              </div>
            </nuxt-link>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    async asyncData({ $content, params, }){
        const articles = await $content('blog', params.slug)
            .only(['title', 'description', 'img', 'slug'])
            .sortBy('createdAt', 'asc')
            .fetch();

            return{
                articles
            }
    }
}
</script>

<style scoped>
/* .post-page {
  padding: 50px 30px;
} */
h2 {
  margin-bottom: 30px;
  text-align: center;
}

/* NAVBAR */
ul{
    list-style: none;
}

.blogdiv{
  text-decoration: none;
  color: #fff;
}

/* ====Navbar==== */
.navbar{
    display: flex;
    justify-content: space-between;
    height: 80px;
    align-items: center;
    padding: 0 20px;
}

.navbar .title{
    margin-right: 50px;
    font-size: 14px;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 500;
    padding: 0 10px;
}

.navbar .title h2{
  margin: 0;
}

.navbar .categories{
  margin-left: 58rem;
}

.navbar .categories ul li{
  display: inline-block;
  padding: 0 20px;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: 500;
  border: 1px solid #6c757d;
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
}

.navbar .categories ul li:hover{
  border-top-left-radius: 0px;
  border-bottom-right-radius: 0px;
  border-top-right-radius: 10px;
  border-bottom-left-radius: 10px;
}

.navbar .menu{
  margin-right: 50px;
}

.cards{
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(400px,1fr));
    padding: 20px;
    grid-gap: 40px;
}
.card{
    background-color: #1c1b29;
    border-radius: 20px;
    box-shadow: 0 0 30px rgba(0,0,0,0.18);
    -webkit-transition: all, 0.3s;
    -o-transition: all, 0.3s;
    transition: all, 0.3s;
    cursor: pointer;
}

.card:hover{
  transform: scale(1.02);
	-webkit-box-shadow: 0px 3px 30px rgba(22, 41, 124, 0.1);
	box-shadow: 0px 3px 30px rgba(22, 41, 124, 0.1);
}
.container{
    position: relative;
    clip-path: polygon(0 0,100% 0, 100% 85%, 0 100%);
}
img{
    width: 100%;
    display: block;
    border-radius: 20px 20px 0 0;
}
.card1 .link .container:after{
    content: "";
    height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    border-radius: 20px 20px 0 0;
    opacity: 0.7;
}
.card1 .link>.container:after{
    background-image: linear-gradient(
        135deg,
        #001845,
        #001233
    );
}
.details{
    padding: 20px 10px;
}
.details h3{
    color: #ffffff;
    font-weight: 600;
    font-size: 18px;
    margin: 10px 0 15px 0;
}
.details p{
    color: #a0a0a0;
    font-size: 15px;
    line-height: 30px;
    font-weight: 400;
}
</style>