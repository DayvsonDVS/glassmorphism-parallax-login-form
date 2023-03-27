<template>
  <section>
    <div class="container">
      <div id="scene">
        <div class="layer" data-depth-x="-0.5" data-depth-y="0.25">
          <img src="@/images/moon.png" />
        </div>

        <div class="layer" data-depth-x="0.15">
          <img src="@/images/mountains02.png" />
        </div>

        <div class="layer" data-depth-x="0.25">
          <img src="@/images/mountains01.png" />
        </div>

        <div class="layer" data-depth-x="-0.25">
          <img src="@/images/road.png" />
        </div>
      </div>
    </div>

    <div class="login">
      <h2>Sign In</h2>
      <div class="inputBox">
        <input type="text" placeholder="Username" />
      </div>

      <div class="inputBox">
        <input type="password" placeholder="Password" />
      </div>

      <div class="inputBox">
        <input type="submit" value="Login" id="btn" />
      </div>

      <div class="group">
        <a href="#"> Forget Password</a>
        <a href="#"> Signup</a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import '@/assets/scss/main.scss'
import parallax from 'parallax-js'

onMounted(() => {
  let scene = document.getElementById('scene')
  let parallaxInstance = new parallax(scene!)
})
</script>

<style scoped lang="scss">
section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100;
  height: 100vh;
  overflow: hidden;
  .container {
    position: absolute;
    left: -10%;
    width: 120%;
    height: 100vh;
    background: url(@/images/bg.jpg);
    #scene .layer {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      img {
        position: absolute;
        bottom: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
  .login {
    position: relative;
    padding: 60px;
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(25px);
    border: 1px solid rgba(255, 255, 255, 0.5);
    border-bottom: 1px solid rgba(255, 255, 255, 0.25);
    border-left: 1px solid rgba(255, 255, 255, 0.25);
    border-radius: 20px;
    width: 500px;
    display: flex;
    flex-direction: column;
    gap: 30px;
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.1);
    h2 {
      position: relative;
      width: 100%;
      text-align: center;
      font-size: 2.5em;
      font-weight: 600;
      color: #fff;
      margin-bottom: 10px;
    }
    .inputBox {
      position: relative;
      input {
        position: relative;
        width: 100%;
        padding: 15px 20px;
        outline: none;
        font-size: 1.25em;
        color: #fff;
        border-radius: 5px;
        background: rgba(0, 0, 0, 0.2);
        box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.25);
        border: 1px solid rgba(0, 0, 0, 0.5);
      }
      #btn {
        position: relative;
        border: none;
        outline: none;
        background: linear-gradient(0deg, #2c3c99, #00b0ff);
        cursor: pointer;
        color: #fff;
        font-weight: 500;
        box-shadow: none;
        transition: 0.5s;
      }
    }
    ::placeholder {
      color: rgba(255, 255, 255, 0.5);
    }
    .group {
      display: flex;
      justify-content: space-between;
      a {
        text-decoration: none;
        font-size: 1.25em;
        color: #fff;
        &:nth-child(2) {
          text-decoration: underline;
        }
      }
    }
  }
}
</style>
