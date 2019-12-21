<template>
  <div>
    <div class=" absolute bottom-0 bg-white w-full flex player-container">
      <div style="width: 250px;min-width: 250px;">
        <div class="flex">
          <img class="rounded-lg h-20 m-2" :src="this.image" />
          <div class="my-auto">
            <div class="text-md font-bold text-dark-blue select-none">
              Lorde-Melodrama
            </div>
            <div class="text-md font-bold text-light-blue select-none">
              Pop Music
            </div>
          </div>
        </div>
      </div>
      <div class="my-auto px-5" style="width: 200px;min-width: 200px;">
        <div class="flex">
          <div class=" my-auto">
            <img src="/icons/previous.svg" alt="" srcset="" />
          </div>
          <div class="my-auto px-2">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              width="90"
              height="90"
              viewBox="0 0 105 105"
            >
              <defs>
                <style>
                  .a {
                    fill: #f8f8f8;
                  }
                  .b {
                    fill: #040e45;
                  }
                  .c {
                    filter: url(#a);
                  }
                </style>
                <filter
                  id="a"
                  x="0"
                  y="0"
                  width="105"
                  height="105"
                  filterUnits="userSpaceOnUse"
                >
                  <feOffset dy="3" input="SourceAlpha" />
                  <feGaussianBlur stdDeviation="7.5" result="b" />
                  <feFlood flood-opacity="0.161" />
                  <feComposite operator="in" in2="b" />
                  <feComposite in="SourceGraphic" />
                </filter>
              </defs>
              <g transform="translate(-227.5 -53.5)">
                <g class="c" transform="matrix(1, 0, 0, 1, 227.5, 53.5)">
                  <path
                    class="a"
                    d="M30,0A29.968,29.968,0,1,1,8.777,8.777,30,30,0,0,1,30,0Z"
                    transform="translate(22.5 19.5)"
                  />
                </g>
                <path
                  class="b"
                  d="M25,42.038V21.024a2.149,2.149,0,0,1,3.374-1.639l13.2,10.507a2.113,2.113,0,0,1,.1,3.181l-13.4,10.6A2.091,2.091,0,0,1,25,42.038Z"
                  transform="translate(248.179 71.469)"
                />
              </g>
            </svg>
          </div>
          <div class=" my-auto">
            <img src="/icons/forward.svg" alt="" srcset="" />
          </div>
        </div>
      </div>
      <div class="w-full my-auto flex">
        <div class="px-3">1:30</div>
        <div class="relative w-full">
          <div class="slider-container">
            <div>
              <span class="bar" id="playerbar"> </span>
            </div>
            <input
              class="slider"
              min="0"
              max="1000"
              value="0"
              type="range"
              @input="sliderMove"
              id="slider"
            />
          </div>
        </div>
        <div class="px-3">3:20</div>
      </div>
      <div class="flex" style="width:250px;min-width: 250px;">
        <div class="my-auto mx-3">
          <img width="40px" src="/icons/volume.svg" alt="" srcset="" />
        </div>
        <div class="relative w-full my-auto">
          <div class="relative flex">
            <div>
              <span class="audio-bar w-10"> </span>
            </div>
            <input
              class="audio-slider"
              min="0"
              max="100"
              value="0"
              type="range"
              @input="audiosliderMove"
            />
          </div>
        </div>
        <div class="my-auto mx-3">
          <img width="40px" src="/icons/repeat-one.svg" alt="" srcset="" />
        </div>
        <div class="my-auto mx-3">
          <img width="40px" src="/icons/playlist.svg" alt="" srcset="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      image: "/img/album-cover.jpg",
      carouselx: 0
    };
  },
  methods: {
    sliderMove() {
      let value = document.getElementById("slider").value;
      let newValue = value / 10;
      let minValue = newValue - 1;
      let maxValue = newValue + 1;
      let bar = document.getElementById("playerbar");
      bar.style.width = newValue + "%";
      if (newValue > 95) {
        bar.style.width = minValue + "%";
      } else if (newValue < 5) {
        bar.style.width = maxValue + "%";
      }
    },
    audiosliderMove() {}
  }
};
</script>

<style scoped>
.player-container {
  box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.17);
  background-color: #f6f7f9;
}
/* sider css */
.slider-container {
  position: relative;
}
.slider {
  background-color: #d9dfe9;
}
.bar {
  position: absolute;
  top: 11px;
  background-color: #2263fe;
  background-image: linear-gradient(-90deg, #2163fe 0%, #3131f3 100%);
  box-shadow: 0 0px 15px 0 rgba(49, 84, 206, 0.76);
  border-radius: 5px 0px 0px 5px;
  height: 7px;
}
.slider-container .slider {
  -webkit-appearance: none;
  width: 100%;
  height: 7px;
  border-radius: 5px;
  outline: none;
}
.slider-container .slider::-webkit-slider-thumb {
  position: relative;
  -webkit-appearance: none;
  width: 20px;
  height: 20px;
  background-color: #2262fe;
  border-radius: 50%;
  -webkit-user-select: none;
  user-select: none;
  cursor: pointer;
  outline: none;
}

/* audio porfiles */
.audio-slider {
  background-color: #d9dfe9;
}
.audio-bar {
  position: absolute;
  background-color: #040e45;
  border-radius: 5px 0px 0px 5px;
  height: 4px;
}
.audio-slider {
  -webkit-appearance: none;
  width: 100%;
  height: 4px;
  border-radius: 5px;
  outline: none;
}
.audio-slider::-webkit-slider-thumb {
  position: relative;
  -webkit-appearance: none;
  width: 10px;
  height: 10px;
  background-color: #040e45;
  border-radius: 50%;
  -webkit-user-select: none;
  user-select: none;
  cursor: pointer;
  outline: none;
}
</style>
