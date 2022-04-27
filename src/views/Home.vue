<template>
  <div class="home">
    <div id="text-test" data-text="Dweb工作室">Dweb工作室</div>
    <canvas id="canvas" width="600" height="600" style="border: 1px solid #000"></canvas>
  </div>
</template>

<script setup lang="ts">
import xbonedata from "../assets/data/export_data(13).json";
import { Xbone } from "xbone";
import { onMounted } from "@vue/runtime-core";
let xbone: Xbone;

onMounted(() => {
  xboneInit(xbonedata);
});

function xboneInit(xbonedata: any) {
  let canvas = <HTMLCanvasElement>document.getElementById("canvas");
  let width = canvas!.clientWidth;
  let height = canvas!.clientHeight;
  let ctx = canvas!.getContext("2d");
  let option = {
    ctx: ctx,
    data: xbonedata,
    width: width,
    height: height,
    animeCall: (anime_gridList = []) => {
      if (anime_gridList.length > 0) {
        xbone.reloadImgDraw(anime_gridList);
      } else {
        xbone.reloadImgDraw();
      }
    },
    clientScene: "web",
  };
  xbone = new Xbone(option);
}
</script>

<style scoped>
.home {
  width: 100%;
  height: 100vh;
  background-color: #000;

  display: flex;
  justify-content: center;
  align-items: center;
  /* text-align: center; */
}

#text-test {
  position: relative;
  padding: 30px;
  font-size: 45px;
  font-weight: 700;
  color: #fff;
  letter-spacing: 2px;
  transform: scale(2);
  cursor: pointer;
}

#text-test::before,
#text-test::after {
  position: absolute;
  content: attr(data-text);
  padding: 30px;
  width: 100%;
  height: 100%;
  top: 0;
  background-color: #000;
  color: #fff;
  overflow: hidden;
}

#text-test::before {
  left: 3px;
  text-shadow: -2px 0 red;
  animation: glitch-1 2s 0s linear infinite;
}

#text-test::after {
  left: -3px;
  text-shadow: -2px 0 blue;
  animation: glitch-2 3s 0s linear infinite;
}

@keyframes glitch-1 {
  0% {
    clip: rect(132px, 350px, 101px, 30px);
  }

  5% {
    clip: rect(17px, 350px, 94px, 30px);
  }

  10% {
    clip: rect(40px, 350px, 66px, 30px);
  }

  15% {
    clip: rect(87px, 350px, 82px, 30px);
  }

  20% {
    clip: rect(137px, 350px, 61px, 30px);
  }

  25% {
    clip: rect(34px, 350px, 14px, 30px);
  }

  30% {
    clip: rect(133px, 350px, 74px, 30px);
  }

  35% {
    clip: rect(76px, 350px, 107px, 30px);
  }

  40% {
    clip: rect(59px, 350px, 130px, 30px);
  }

  45% {
    clip: rect(29px, 350px, 84px, 30px);
  }

  50% {
    clip: rect(22px, 350px, 67px, 30px);
  }

  55% {
    clip: rect(67px, 350px, 62px, 30px);
  }

  60% {
    clip: rect(10px, 350px, 105px, 30px);
  }

  65% {
    clip: rect(141px, 350px, 74px, 30px);
  }

  70% {
    clip: rect(20px, 350px, 78px, 30px);
  }

  75% {
    clip: rect(15px, 350px, 75px, 30px);
  }

  80% {
    clip: rect(66px, 350px, 39px, 30px);
  }

  85% {
    clip: rect(133px, 350px, 73px, 30px);
  }

  90% {
    clip: rect(36px, 350px, 128px, 30px);
  }

  95% {
    clip: rect(68px, 350px, 103px, 30px);
  }

  100% {
    clip: rect(14px, 350px, 100px, 30px);
  }
}

@keyframes glitch-2 {
  0% {
    clip: rect(120px, 350px, 36px, 30px);
  }

  5% {
    clip: rect(36px, 350px, 4px, 30px);
  }

  10% {
    clip: rect(85px, 350px, 66px, 30px);
  }

  15% {
    clip: rect(91px, 350px, 91px, 30px);
  }

  20% {
    clip: rect(148px, 350px, 138px, 30px);
  }

  25% {
    clip: rect(38px, 350px, 122px, 30px);
  }

  30% {
    clip: rect(69px, 350px, 54px, 30px);
  }

  35% {
    clip: rect(98px, 350px, 71px, 30px);
  }

  40% {
    clip: rect(146px, 350px, 34px, 30px);
  }

  45% {
    clip: rect(134px, 350px, 43px, 30px);
  }

  50% {
    clip: rect(102px, 350px, 80px, 30px);
  }

  55% {
    clip: rect(119px, 350px, 44px, 30px);
  }

  60% {
    clip: rect(106px, 350px, 99px, 30px);
  }

  65% {
    clip: rect(141px, 350px, 74px, 30px);
  }

  70% {
    clip: rect(20px, 350px, 78px, 30px);
  }

  75% {
    clip: rect(133px, 350px, 79px, 30px);
  }

  80% {
    clip: rect(78px, 350px, 52px, 30px);
  }

  85% {
    clip: rect(35px, 350px, 39px, 30px);
  }

  90% {
    clip: rect(67px, 350px, 70px, 30px);
  }

  95% {
    clip: rect(71px, 350px, 103px, 30px);
  }

  100% {
    clip: rect(83px, 350px, 40px, 30px);
  }
}
</style>
