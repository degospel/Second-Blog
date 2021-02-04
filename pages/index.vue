<template>
  <div class="container">
    <div class="wrapper">
      <div class="bg"></div>

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
                      <NuxtLink to="/post" class="blogdiv">Post</NuxtLink>
                  </li>
              </ul>
          </div>
      </nav>

      <!-- Social-Media -->
      <div class="media">
          <ul>
              <li>Facebook</li>
              <li>Twitter</li>
              <li>Instagram</li>
          </ul>
      </div>

      <!-- Imagex -->
      <div class="img-wrapper01">
          <div class="img01"></div>
          <div class="block"></div>
      </div>

      <div class="img-wrapper02">
          <div class="img02"></div>
          <div class="block"></div>
      </div>

      <!-- Text -->
      <div class="text">
          <h1>
              <span class="hidetext">The Great Escape</span>
          </h1>
          <p>
              <span class="hidetext">Issue two out now</span>
          </p>
      </div>

      <!-- Desc -->
      <div class="desc">
          <ul>
              <li>Volume 01</li>
              <li>Volume 02</li>
          </ul>

          <p>
              A fashion insight into leading summer styles,
              travel destinations to may never of thought of,
              a beginners guide to S&M and much much more.
          </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
} */

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

/* ====Social-Media==== */
.media{
  position: absolute;
  top: 350px;
  right: -90px;
  transform: rotate(-90deg);
}

.media ul li{
  display: inline-block;
  padding: 0 20px;
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 1px;
}
/* ====Imagex==== */
.img-wrapper01{
  position: absolute;
  top: 100px;
  left: 160px;
}

.img-wrapper01 .img01{
  background: url('~assets/img/img1.jpg') no-repeat;
  background-position: 50%;
  background-size: cover;
  height: 450px;
  width: 400px;
  opacity: 0;
  animation: image-appear 0.0001s linear forwards;
  animation-delay: 2.2s;
}

.img-wrapper02{
  position: absolute;
  top: 0;
  left: 650px;
}

.img-wrapper02 .img02{
  background: url('~assets/img/img2.jpg') no-repeat;
  background-position: 50%;
  background-size: cover;
  height: 100vh;
  width: 600px;
  opacity: 0;
  animation: image-appear 0.0001s linear forwards;
  animation-delay: 2.4s;
}

@keyframes image-appear {
  0%{
      opacity: 0;
  }
  100%{
      opacity: 1;
  }
}
.block{
  position: absolute;
  top: 0;
  left: 0;
  width: 0%;
  height: 100%;
  background: #6c757d;
  animation: block-appear 1.5s cubic-bezier(0.19, 1, 0.22, 1) forwards;
  animation-delay: 1.3s;
}

.img-wrapper02 .block{
    animation-delay: 1.8s;
}

@keyframes block-appear {
  0% {
      left: 0;
      width: 0%;
  }
  50% {
      left: 0;
      width: 100%;
  }
  100% {
      left: 100%;
      width: 0%;
  }
}

/* ====Text==== */
.text{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  white-space: nowrap;
  width: 1000px;
}

.text h1{
  font-size: 120px;
  font-family: 'Tinos';
  font-weight: lighter;
  letter-spacing: 5px;
  position: relative;
  /* overflow: hidden; */
  height: 120px;
  width: 100%;
}

.text h1 .hidetext{
  position: absolute;
}

.text p{
  font-size: 40px;
  font-family: 'Tinos';
  text-transform: uppercase;
  letter-spacing: 5px;
  font-weight: lighter;
  position: relative;
  overflow: hidden;
  height: 50px;
  width: 100%;
}

.text p .hidetext{
    position: absolute;
}

/* ====Desc==== */
.desc{
    position: absolute;
    left: 200px;
    bottom: 70px;
    display: flex;    
}

.desc ul{
    margin-right: 50px;
}

.desc ul li{
    font-size: 10px;
    letter-spacing: 1px;
    font-weight: 500;
    border-bottom: 1px solid #fff;
    margin-bottom: 10px;
}

.desc p{
    width: 250px;
    font-size: 10px;
    font-weight: 300;
    line-height: 2;
}
</style>
