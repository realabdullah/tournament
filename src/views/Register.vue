<template>
  <Navbar />
  <div class="login-root">
    <div class="box-root flex-flex flex-direction--column" style="min-height: 100vh;flex-grow: 1;">
      <div class="box-root padding-top--24 flex-flex flex-direction--column" style="flex-grow: 1; z-index: 9;">
        <div class="formbg-outer">
          <div class="formbg">
            <div class="formbg-inner padding-horizontal--48">
              <span class="padding-bottom--15">Register to participate</span>
              <form id="stripe-login" @submit.prevent="signUp">
                <div class="field padding-bottom--24">
                  <label for="email">Email</label>
                  <input type="email" name="email" v-model="email">
                </div>
                <div class="field padding-bottom--24">
                  <label for="username">Name</label>
                  <input type="text" name="username" v-model="username">
                </div>
                <div class="field padding-bottom--24">
                  <label for="faculty">Faculty</label>
                  <input type="text" name="faculty" v-model="faculty">
                </div>
                <div class="field padding-bottom--24">
                  <label for="department">Department</label>
                  <input type="text" name="department" v-model="department">
                </div>
                <div class="field padding-bottom--24">
                  <label for="phone">Mobile Number</label>
                  <input type="telephone" name="phone" v-model="phone">
                </div>
                <div class="field padding-bottom--24">
                  <label for="game">Game to play</label>
                  <input type="text" name="game" v-model="game">
                </div>
                <div class="field padding-bottom--24">
                  <label for="userId">UserId</label>
                  <input type="text" name="userId" v-model="userId">
                </div>
                <div class="field padding-bottom--24"><button class="submi" v-if="loading">
                    <svg width="38" height="38" viewBox="0 0 38 38" xmlns="http://www.w3.org/2000/svg" stroke="#fff">
                      <g fill="none" fill-rule="evenodd">
                        <g transform="translate(1 1)" stroke-width="2">
                          <circle stroke-opacity=".5" cx="18" cy="18" r="18"/>
                          <path d="M36 18c0-9.94-8.06-18-18-18">
                            <animateTransform
                                attributeName="transform"
                                type="rotate"
                                from="0 18 18"
                                to="360 18 18"
                                dur="1s"
                                repeatCount="indefinite"/>
                          </path>
                        </g>
                    </g>
                  </svg>
                  </button>
                  <button class="submit" v-else>Sign Up</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>

<style>
.submi {
  padding: 5px 16px;
  width: 100%;
  min-height: 44px;
  border: unset;
  border-radius: 4px;
  background-color: #353030;
  box-shadow: rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0.12) 0px 1px 1px 0px, 
              #353030 0px 0px 0px 1px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(60, 66, 87, 0.08) 0px 2px 5px 0px;
  color: #fff;
  font-weight: 600;
  cursor: pointer;
}
.submi svg {
  width: 25px;
}
a {
  color: #353030;
  text-decoration: unset;
}
.login-root {
    display: flex;
    width: 100%;
    min-height: 100vh;
    overflow: hidden;
}

.flex-flex {
    display: flex;
}
.align-center {
  align-items: center; 
}
.center-center {
  align-items: center;
  justify-content: center;
}
.box-root {
    box-sizing: border-box;
}
.flex-direction--column {
    -ms-flex-direction: column;
    flex-direction: column;
}

.padding-top--64 {
  padding-top: 64px;
}
.padding-top--48 {
  padding-top: 48px;
}
.padding-bottom--24 {
  padding-bottom: 24px;
}
.padding-horizontal--48 {
  padding: 48px;
}
.padding-bottom--15 {
  padding-bottom: 15px;
}
.flex-justifyContent--center {
  -ms-flex-pack: center;
  justify-content: center;
}

span {
    display: block;
    font-size: 20px;
    line-height: 28px;
    color: #1a1f36;
}
label {
    margin-bottom: 10px;
}
.grid--50-50 {
    display: grid;
    grid-template-columns: 50% 50%;
    align-items: center;
}
.field input {
    font-size: 16px;
    line-height: 28px;
    padding: 8px 16px;
    width: 100%;
    min-height: 44px;
    border: unset;
    border-radius: 4px;
    outline-color: rgb(84 105 212 / 0.5);
    background-color: rgb(255, 255, 255);
    box-shadow: rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
                rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
                rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
                rgba(60, 66, 87, 0.16) 0px 0px 0px 1px, 
                rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
                rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
                rgba(0, 0, 0, 0) 0px 0px 0px 0px;
}
.submit {
  font-size: 16px;
  line-height: 28px;
  padding: 8px 16px;
  width: 100%;
  min-height: 44px;
  border: unset;
  border-radius: 4px;
  background-color: #353030;
  box-shadow: rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0.12) 0px 1px 1px 0px, 
              #353030 0px 0px 0px 1px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(0, 0, 0, 0) 0px 0px 0px 0px, 
              rgba(60, 66, 87, 0.08) 0px 2px 5px 0px;
  color: #fff;
  font-weight: 600;
  cursor: pointer;
}
.field-checkbox input {
    width: 20px;
    height: 15px;
    margin-right: 5px; 
    box-shadow: unset;
    min-height: unset;
}
.field-checkbox label {
    display: flex;
    align-items: center;
    margin: 0;
}
a.ssolink {
    display: block;
    text-align: center;
    font-weight: 600;
}
.footer-link span {
    font-size: 14px;
    text-align: center;
}
.listing a {
    color: #697386;
    font-weight: 600;
    margin: 0 10px;
}
.animationRightLeft {
  animation: animationRightLeft 2s ease-in-out infinite;
}
.animationLeftRight {
  animation: animationLeftRight 2s ease-in-out infinite;
}
.tans3s {
  animation: animationLeftRight 3s ease-in-out infinite;
}
.tans4s {
  animation: animationLeftRight 4s ease-in-out infinite;
}
@keyframes animationLeftRight {
  0% {
    transform: translateX(0px);
  }
  50% {
    transform: translateX(1000px);
  }
  100% {
    transform: translateX(0px);
  }
} 
@keyframes animationRightLeft {
  0% {
    transform: translateX(0px);
  }
  50% {
    transform: translateX(-1000px);
  }
  100% {
    transform: translateX(0px);
  }
} 
</style>