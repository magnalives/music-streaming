<template>
  <div>
    <div class="bg-white shadow-md py-5 flex">
      <button @click="switchNav" class="focus:outline-none">
        <div class="ml-5">
          <svg
            version="1.1"
            id="Layer_1"
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="30px"
            height="30px"
            viewBox="0 0 64 64"
          >
            <g>
              <g>
                <g>
                  <g>
                    <path
                      d="M60,16H4c-2.2,0-4-1.8-4-4v0c0-2.2,1.8-4,4-4h56c2.2,0,4,1.8,4,4v0C64,14.2,62.2,16,60,16z"
                    />
                  </g>
                </g>
              </g>
              <g>
                <g>
                  <g>
                    <path
                      d="M60,56H4c-2.2,0-4-1.8-4-4v0c0-2.2,1.8-4,4-4h56c2.2,0,4,1.8,4,4v0C64,54.2,62.2,56,60,56z"
                    />
                  </g>
                </g>
              </g>
              <g>
                <g>
                  <g>
                    <path
                      d="M60,36H4c-2.2,0-4-1.8-4-4v0c0-2.2,1.8-4,4-4h56c2.2,0,4,1.8,4,4v0C64,34.2,62.2,36,60,36z"
                    />
                  </g>
                </g>
              </g>
            </g>
          </svg>
        </div>
      </button>
    </div>
    <div id="navSlider" class="h-screen border border-gray-400 absolute top-0 z-1 transition-small">
      <div id="navdrawer" class="pt-20 h-full w-drawer">
        <div class="mt-5">
          <nuxt-link to="/">
            <div class="pl-10 py-2 flex items-center nav-list">
              <svg
                version="1.1"
                id="Layer_1"
                xmlns="http://www.w3.org/2000/svg"
                x="0px"
                y="0px"
                width="30px"
                height="30px"
                viewBox="0 0 64 64"
              >
                <g>
                  <g>
                    <g>
                      <g>
                        <polygon points="32,0 0,10 32,21 64,10 				" />
                      </g>
                    </g>
                  </g>
                  <g>
                    <g>
                      <g>
                        <polygon points="0,50 29,62 29,26 0,15 				" />
                      </g>
                    </g>
                  </g>
                  <g>
                    <g>
                      <g>
                        <polygon points="35,62 64,50 64,15 35,26 				" />
                      </g>
                    </g>
                  </g>
                </g>
              </svg>

              <span class="text-md font-semibold pl-5">Home</span>
            </div>
          </nuxt-link>

          <nuxt-link to="/about">
            <div class="pl-10 py-2 flex items-center nav-list">
              <svg
                version="1.1"
                id="Layer_1"
                xmlns="http://www.w3.org/2000/svg"
                x="0px"
                y="0px"
                width="30px"
                height="30px"
                viewBox="0 0 64 64"
              >
                <g>
                  <g>
                    <g>
                      <path
                        fill="#A3A9BD"
                        d="M62,25H16.3c-0.8,0-1.6,0.7-1.9,1.5L3,55h48.5c0.8,0,1.5-0.5,1.8-1.2l10.5-25.6C64.3,26.9,63.3,25,62,25z"
                      />
                    </g>
                  </g>
                  <g>
                    <g>
                      <path
                        d="M13.3,21H57v-7c0-1.1-0.9-2.4-2-2.4H33.3c-0.5,0-1-0.2-1.4-0.6l-3.4-5.4C28.1,5.2,27.6,5,27.1,5H2C0.9,5,0,5.9,0,7v44l11.4-28.5C11.7,21.7,12.5,21,13.3,21z"
                      />
                    </g>
                  </g>
                </g>
              </svg>
              <span class="text-md font-semibold pl-5">About</span>
            </div>
          </nuxt-link>

          <div class="absolute w-full bottom-0">
            <button class="w-full focus:outline-none" @click="minNav">
              <div class="pl-10 py-2 flex items-center nav-list bg-gray-700">
                <svg
                  version="1.1"
                  id="Layer_1"
                  xmlns="http://www.w3.org/2000/svg"
                  x="0px"
                  y="0px"
                  height="30px"
                  width="30px"
                  viewBox="0 0 64 64"
                >
                  <g>
                    <g id="XMLID_8_">
                      <g>
                        <g>
                          <path
                            fill="#FFFFFF"
                            d="M32,0c17.7,0,32,14.3,32,32S49.7,64,32,64S0,49.7,0,32S14.3,0,32,0z"
                          />
                        </g>
                      </g>
                    </g>
                    <g>
                      <g>
                        <path fill="#316CFF" d="M25,19l18,13L25,45V19z" />
                      </g>
                    </g>
                  </g>
                </svg>
                <span class="text-md text-white font-semibold pl-5">Collapse Menu</span>
              </div>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    switchNav() {
      document.getElementById("maincnt").classList.remove("noAnimation");
      const nav = document.getElementById("navSlider");
      const mainCont = document.getElementById("maincnt");
      nav.classList.toggle("transform-x-100");
      mainCont.classList.toggle("noMargin");
    },
    minNav() {
      document.getElementById("maincnt").classList.add("noAnimation");
      document.getElementById("navdrawer").classList.toggle("w-drawer-min");
      document.getElementById("maincnt").classList.toggle("main-min-cnt");
      const minnav = document.getElementsByClassName("nav-list");
      for (let i = 0; i < minnav.length; i++) {
        minnav[i].classList.toggle("min-nav");
      }
    }
  }
};
</script>

<style>
.nuxt-link-exact-active div {
  background-color: #edf2f7;
}
</style>