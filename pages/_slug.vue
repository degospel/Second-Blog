<template>
    <div>
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
                        <NuxtLink to="/post" class="blogdiv"><i class='bx bx-left-arrow'></i>Back</NuxtLink>
                    </li>
                </ul>
            </div>
        </nav>

        <article>
            <nuxt-content :document="article"/>
        </article>
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const article = await $content('blog', params.slug).fetch();

        return { article }
    }
}
</script>

<style>
article {
    display: block;
    margin: 0 auto;
    padding: 50px 30px;
    max-width: 800px;
}

h1{
    font-size: 28px;
    font-weight: 900;
    margin-bottom: 30px;
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
</style>