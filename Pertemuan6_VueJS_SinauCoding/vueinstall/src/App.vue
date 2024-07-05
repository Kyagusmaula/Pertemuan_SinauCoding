<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://fonts.googleapis.com/css?family=Montserrat"
      rel="stylesheet" />
    <title>Task 3</title>
    <link rel="stylesheet" href="./style.css" />
  </head>
  <body>
    <div class="kiri">
      <h2>Welcome to Twitter</h2>
      <p>Happening now, join twitter today</p>
      <img
        src="./Asset/Asset/Ilustrator.svg"
        width="310px"
        height="310px"
        alt="Ilustrator" />
      <div class="footer"><p>© 2022 Twitter, Inc.</p></div>
    </div>
    <div class="kanan">
      <div class="header">
        <img
          src="./Asset/Asset/Logo Twitter.svg"
          width="50px"
          height="50px"
          alt="Logo Twitter" />
        <div clas="signup">
          <p>
            Don't have an account ?
            <a href="####" target="_self" rel="noopener noreferrer">Sign Up</a>
          </p>
        </div>
      </div>
      <div class="content">
        <div class="login">
          <h2>Log in to Twitter</h2>
          <p>Enter Twitter Account</p>
        </div>
        <form>
          <input
            type="text"
            id="phone"
            name="phone"
            placeholder="Phone, email or username" />
          <br />
          <br />
          <input
            type="password"
            id="password"
            name="password"
            placeholder="Password" />
        </form>
        <a href="####" target="_self" rel="noopener noreferrer"
          >Forgot password ?</a
        >
        <div class="signin">
          <button type="submit">Sign In</button>
        </div>
      </div>
      <div class="or">
        <p>or</p>
      </div>
      <div class="signwith">
        <button class="google" type="button">
          <img
            src="./Asset/Asset/Logo Google.svg"
            width="18px"
            height="18px"
            alt="Logo Google" />
          Sign in with Google
        </button>

        <button class="apple" type="button">
          <img
            src="./Asset/Asset/Logo Apple.svg"
            width="20px"
            height="20px"
            alt="Logo Apple" />
          Sign in with Apple
        </button>
      </div>
    </div>
  </body>
</template>

<style scoped>
body {
  display: flex;
  flex-direction: row;
  min-height: 100vh;
}
.kiri {
  background-color: #1e9cf1;
  width: 50%;
  text-align: center;
  justify-content: center;
  align-items: center;
  font-family: "Montserrat", sans-serif;
  color: #ffffff;
  padding-top: 20vh;
}

.kiri h2 {
  margin: 10px;
  font-weight: 900;
  font-size: 32px;
  text-shadow: 0px 0.15px, 0.15px 0px, 0.15px 0.15px;
}

.kiri p {
  margin: 10px;
  font-size: 15px;
  font-weight: 900;
}

.kiri img {
  margin-top: 5px;
}

.footer {
  display: block;
  position: absolute;
  bottom: 5px;
  left: 0;
  width: 50%;
}
.footer p {
  font-size: 13px;
  font-weight: 100;
}

.kanan {
  width: 50%;
  background-color: #ffffff;
  font-family: "Montserrat", sans-serif;
  color: #000;
}
.header {
  margin: 50px 80px 0 70px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.header img {
  display: inline;
}

.header p {
  display: inline;
  font-size: 13px;
  font-weight: 100;

  padding-right: 0;
}
.header a {
  font-size: 13px;
  font-weight: 900;
  color: #1e9cf1;
}
.login {
  margin: 50px 80px 0 70px;
}
.kanan h2 {
  flex-direction: row;
  font-weight: 900;
  font-size: 32px;
  text-shadow: 0px 0.15px, 0.15px 0px, 0.15px 0.15px;
}

.kanan p {
  font-size: 15px;
  font-weight: 900;
}
form {
  margin: 0px 80px 0 70px;
  display: block;
}
form input {
  background-color: #eeeeee;
  color: #757575;
  width: 100%;
  padding: 17px 0;
  border: none;
  text-indent: 15px;
}

.content a {
  display: block;
  margin: 10px 80px 0 70px;
  text-align: right;
  font-size: 13px;
  color: black;
  text-decoration: none;
}

.signin {
  margin: 10px 80px 0 70px;
}

.signin button {
  width: 100%;
  padding: 15px 0;
  background-color: #1e9cf1;
  color: #ffffff;
  border: none;
  text-align: center;
  cursor: pointer;
}

.or {
  text-align: center;
}

.signwith {
  display: flex;
  margin: 0px 80px 0 70px;
  justify-content: space-between;
  align-items: center;
}

.google,
.apple {
  font-weight: 600;
  padding: 12px 40px 15px;
  font-size: 15px;
  align-items: center;
  cursor: pointer;
}

.google {
  border: none;
  text-align: center;
  background-color: #eeeeee;
  color: black;
}
.apple {
  border: none;
  text-align: center;
  background-color: #191d23;
  color: #ffffff;
}
</style>
