<script setup>
import Card from "@/components/Card.vue";
import Typed from "typed.js";
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";
import {faDiscord, faGithub} from "@fortawesome/free-brands-svg-icons";

document.addEventListener("DOMContentLoaded", () => {
  let typed = new Typed('#title-element', {
    strings: [
      "Hi there!",
      "I am Tjorven,",
      "a Software Engineer,",
      "and Student at TU Darmstadt.",
      "Have a look into my profiles :D"
    ],
    typeSpeed: 20,
    startDelay: 50,
    backSpeed: 10,
    smartBackspace: true,
    cursorChar: '',
    onLastStringBackspaced() {
      let audio = new Audio("public/assets/typewriter.wav")
      audio.play();
    },
    onComplete() {
      setTimeout(() => {
        document.getElementById("title-element").remove();
      }, 2000)
    }
  })

  typed.start();
})
</script>

<template>
  <div class="box" id="">
    <div class="d-flex">
      <Card style="height: 100%">
        <template #header>
          <div class="d-flex avatar-box">
            <img alt="Tjorven Liebe" src="/public/assets/img/profile_image.gif"/>
            <span class="title" id="title-element"></span>
          </div>
        </template>
      </Card>
      <div class="firstbox">
      </div>
      <div class="secondbox">
        <div class="infos">
          <div>
            <h1 style="text-align: center; font-size: 40pt">My Profiles</h1>
            <div class="socials">
              <div class="mobile">
                <img alt="Tjorven Liebe" height="60px" src="/public/assets/img/profile_image.gif"/>
              </div>
              <a href="https://discord.com/users/428284027519369217" target="_blank">
                <FontAwesomeIcon :icon="faDiscord"/>
              </a>
              <a href="https://github.com/Tjorven-Liebe/" target="_blank">
                <FontAwesomeIcon :icon="faGithub"/>
              </a>
            </div>
            <br/>
            <br/>
            <div class="socials" style="display: block">
              <h5 style="text-align: center; font-size: 40pt">My Github Stats</h5>
              <img alt="stats" src="https://github-profile-trophy.vercel.app/?username=Tjorven-Liebe&theme=darkhub&margin-w=15&margin-h=15&column=-1&no-bg=true&no-frame=true&rank=-C"/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.box {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 80%;
  max-height: 700px;
  height: 100%;
}

.avatar-box {
  justify-content: left;
  height: 200px;
  z-index: 100;
}

.avatar-box > * {
  margin: auto 0;
  z-index: 100;
}

.avatar-box img {
  margin-left: 10px;
  height: 100%;
}

.infos {
  position: absolute;
  left: 0;
  top: 0;
  width: 500%;
  height: 100%;
}

.socials {
  width: 90%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  font-size: 54pt;
  color: white;
}

.socials a {
  color: white;
}

.socials svg {
  height: 80%;
  width: 90%;
  max-height: 50px;
  max-width: 50px;
  padding: 25px;
}

.mobile {
  display: none;
}

.socials img {
  width: 100%;
}

@media screen and (max-width: 1700px) {
  .avatar-box img {
    margin-left: 0;
  }
}

@media screen and (max-width: 1500px) {
  .avatar-box img {
    margin-left: -20px;
  }
}

@media screen and (max-width: 1400px) {
  #title-element {
    display: none;
  }

  .mobile {
    display: flex;
    position: absolute;
    top: -15px;
    left: 30px;

    img {
      height: 150px;
    }
  }

  .avatar-box img {
    display: none;
  }

  .box {
    width: 95%;
    height: 100%;
    top: 60%
  }

  .secondbox {
    border-radius: 20px;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 80%;
  }

  .infos {
    position: relative;
    width: 100%;
    top: 60%;
    transform: translateY(-50%);
  }

  .firstbox {
    display: none;
  }

  .secondbox::after {
    display: none;
  }
}


@media screen and (max-width: 560px) {
  .mobile {
    display: none ;
  }
}
</style>