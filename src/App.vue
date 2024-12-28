<template>
  <div class="main">
    <h1>Дима Ден с днем рождения</h1>
    <h3> Чтоб хуй стоял и деньги были</h3>
    <div class="gift-box" id="gift-box" @click="changePhoto"></div>
    <div class="ananas" id="ananas">
      <img src="https://sun9-49.userapi.com/impg/YLg9v8eg1xPo9SnuaV_klX7XoyxvMq3h7qiyJQ/_63BVC8bjVI.jpg?size=593x593&quality=95&sign=7a5d80e8fad1d1c7964c99c3d24dc2db&type=album" alt="">
    </div>
    <div class="hehe" id="hehe">
      А ХУЙ ТЫ УГАДАЛ
    </div>
    <div class="video" id="video">
        <video src="https://cdn.mtdv.me/video/rick.mp4" loop="" poster="" id="rick-video" width="1080" controls></video>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue"
function changePhoto() {
  confetti()
  document.getElementById('ananas').style.display = "block"
  setTimeout(() => {
    changeHehe();
  }, 3000);
}

function changeHehe() {
  document.getElementById('hehe').style.display = "block"
  setTimeout(() => {
    changeVideo();
  }, 1000);
}

function changeVideo() {
    let video = document.getElementById('rick-video');
    document.getElementById('video').style.display = "block"
    setTimeout(() => {
        video.play();
    }, 100);
};
 function confetti(e) {

 new confettiKit({
 confettiCount: 40,
 angle: 90,
 startVelocity: 50,
 colors: randomColor({hue: 'blue',count: 18}),
 elements: {
 'confetti': {
 direction: 'down',
 rotation: true,
 },
 'star': {
 count: 10,
 direction: 'down',
 rotation: true,
 },
 'ribbon': {
 count: 5,
 direction: 'down',
 rotation: true,
 },
 'custom': [{
 count: 1,
 width: 50,
 textSize: 15,
 content: '//bootstraptema.ru/snippets/effect/2018/confettikit/shar.png',
 contentType: 'image',
 direction: 'up',
 rotation: false,
 }]
 },
 position: 'bottomLeftRight',
 });
 };

</script>

<style>
  .main {
    width: 100vw;
    height: 100vh;
    background-color: #1f1f1f;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  h1 {
    position: absolute;
    left: 50%;
    top: 25%;
    transform: translate(-50%, -50%);
  }
  h3 {
    position: absolute;
    left: 50%;
    top: 30%;
    transform: translate(-50%, -50%);
  }
.gift-box {
    background-color: initial;
    position: relative;
    width: 300px;
    height: 300px;
    background: url(https://cdn.mtdv.me/images/presents.png) no-repeat center center;
    background-size: contain;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    animation: bounce 2s infinite;
}

.video {
  position: absolute;
  display: none;
}

.ananas {
  position: absolute;
  display: none;
}

.hehe {
  position: absolute;
  display: none;
  background-color: black;
  font-size: 100px;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
}
40% {
    transform: translateY(-20px);
}
60% {
    transform: translateY(-10px);
}
}
</style>
