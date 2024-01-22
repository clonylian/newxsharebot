<template>
  <div class="yhome">
    <div class="yhomey flex yhomeyshow">
      <div class="yhomey_one">
        <p class="yhomey_two">{{ $store.state.txt.yhome }}</p>
        <h1 class="yhomey_three">
          {{ $store.state.txt.yhometitle }}
        </h1>
        <p class="yhomey_four">
          {{ $store.state.txt.yhomecont }}
        </p>
        <h1 class="yhomey_three">{{ $store.state.txt.yhometitlet }}</h1>
        <p class="yhomey_four">{{ $store.state.txt.yhomecontt }}</p>
        <div class="yhomey_inpbox flex">
          <div class="yhomeyinpy">
            <input
              type="text"
              v-model="yzminpy"
              maxlength="1"
              ref="input1"
              @keydown="yzminp($event, 1, yzminpy)"
              @input="xiqian(1, yzminpy)"
            />
          </div>
          <div class="yhomeyinpy">
            <input
              type="text"
              v-model="yzminpt"
              maxlength="1"
              ref="input2"
              @input="xiqian(2, yzminpt)"
              @keydown="yzminp($event, 2, yzminpt)"
            />
          </div>
          <div class="yhomeyinpy">
            <input
              type="text"
              v-model="yzminpthr"
              maxlength="1"
              ref="input3"
              @input="xiqian(3, yzminpthr)"
              @keydown="yzminp($event, 3, yzminpt)"
            />
          </div>
          <div class="yhomeyinpy">
            <input
              type="text"
              v-model="yzminpf"
              maxlength="1"
              ref="input4"
              @input="xiqian(4, yzminpf)"
              @keydown="yzminp($event, 4, yzminpt)"
              routz
            />
          </div>
          <div class="yhomeyinpy">
            <input
              type="text"
              v-model="yzminpw"
              maxlength="1"
              ref="input5"
              @input="xiqian(5, yzminpw)"
              @keydown="yzminp($event, 5, yzminpt)"
            />
          </div>
        </div>
        <div class="yhomey_but flex">
          <button :class="logari == '1' ? 'shiactive' : ''" @click="routz()">
            {{ anntxt }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import md5 from "blueimp-md5";
import { ref, onMounted } from "vue";
import { useStore } from "vuex";
import { useRouter } from "vue-router";
const router = useRouter();
const store = useStore();
let yzminpy = ref("");
let yzminpt = ref("");
let yzminpthr = ref("");
let yzminpf = ref("");
let yzminpw = ref("");
let logari = ref("0");
let xhladd = ref("");
let input5 = ref(null);
let input4 = ref(null);
let input3 = ref(null);
let input2 = ref(null);
let input1 = ref(null);
let anntxt = ref("ENTER INVITE CODE");
onMounted(() => {
  console.log(input5.value);
  console.log(input4.value);
  console.log(input3.value);
  console.log(input2.value);
  console.log(input1.value);
});
let routz = () => {
  let values =
    yzminpy.value +
    yzminpt.value +
    yzminpthr.value +
    yzminpf.value +
    yzminpw.value;
  logari.value = "1";
  let length = values.length;
  let sign = md5(xhladd.value + "88888888");
  let walletadd = xhladd;
  // if (length == 5 && localStorage.getItem("xhladd")) {
  //   api
  //     .login({
  //       appId: "xbot",
  //       sign: sign,
  //       walletAddress: walletadd,
  //     })
  //     .then((res) => {
  //       console.log(res);
  //       localStorage.setItem("user", JSON.stringify(res.data.data));
  //       api
  //         .verifyinvitation({
  //           invitationCode: "ZVKMN",
  //           appId: "xbot",
  //           userId: res.data.data.userId,
  //           token: res.data.data.token,
  //         })
  //         .then((res) => {
  //           console.log("verifyinvitation", res.data.status);
  //           if (res.data.status == "success") {
  //             $router.push("/Airdrop");
  //           }
  //         });
  //     });
  // } else if (localStorage.getItem("xhladd") && length != 5) {
  //   alert("Please enter the correct invitation code!!!");
  // } else {
  //   alert("Please link the wallet first!!!");
  // }
  router.push("/Airdrop");
  localStorage.setItem("istrue", "1");
};
let yzminp = (event, currentInput) => {
  const key = event.keyCode || event.which;
  if (key === 8 && event.target.value === "") {
    if (currentInput == 5) {
      input4.value.focus();
    } else if (currentInput == 4) {
      input3.value.focus();
    } else if (currentInput == 3) {
      input2.value.focus();
    } else if (currentInput == 2) {
      input1.value.focus();
    }
  }
};
let xiqian = (index, val) => {
  if (val != "") {
    if (index == 1) {
      input2.value.focus();
    } else if (index == 2) {
      input3.value.focus();
    } else if (index == 3) {
      input4.value.focus();
    } else if (index == 4) {
      input5.value.focus();
    }
  }
  let values =
    yzminpy.value +
    yzminpt.value +
    yzminpthr.value +
    yzminpf.value +
    yzminpw.value;
  let length = values.length;
  if (length == 5) {
    anntxt.value = "REDEEM INVITE CODE";
  } else {
    anntxt.value = "ENTER INVITE CODE";
  }
};
</script>

<style scoped>
.ymainhy .yhome {
  background: rgb(235 235 235);
  background: url("../assets/homebgw.png");
  overflow: auto;
}

.yhome {
  width: 100%;
  overflow: auto;
  padding-top: 6rem;
  background: rgb(30, 37, 43);
}
.yhomey {
  width: 63.5%;
  height: auto;
  margin: 0 auto;
  padding-top: 5rem;
  position: relative;
  opacity: 0.05;
  transition: opacity 1s linear;
}
.yhomeyshow {
  opacity: 1;
}
.yhomeyleft {
  width: 34.25rem;
  height: 100%;
}

.yhomeyright {
  position: absolute;
  top: 10.5rem;
  right: 0;
}

.yhomeyright > p {
  font-family: "Vectrex";
  font-size: 2.5rem;
  font-weight: 400;
  font-style: normal;
  text-align: right;
  line-height: 1.5;
  color: rgb(255, 255, 255);
  text-shadow: rgb(237, 77, 19) 0px 0px 25px, rgb(237, 77, 19) 0px 0px 50px;
}

.ymainhy .yhomeyright > p {
  color: rgb(17, 11, 11);
}

.yhomeytxtc {
  font-family: "Vectrex";
  font-size: 1.375rem;
  font-weight: 400;
  font-style: normal;
  text-align: right;
  line-height: 1.75rem;
  color: rgb(255, 255, 255);
  margin-top: 0.75rem;
}

.ymainhy .yhomeytxtc {
  color: rgb(17, 11, 11);
}

.yhomeytxtc span {
  color: rgb(237 77 19);
}

.yhomeyright a {
  display: flex;
  margin-top: 2rem;
  flex-direction: row-reverse;
}

.yhomeyright a svg {
  width: 23.375rem;
  height: 6.5rem;
  transition: all 0.3s;
}

.yhomeyright a svg:hover {
  transform: scale(1.05);
}
.ymianbt {
  background-color: rgb(17, 11, 11);
}
.yhomey_but {
  justify-content: center;
}
.yhomey_but button {
  font-family: "Poppins";
  border-radius: 1rem;
  height: 3.5rem;
  padding: 0 1.5rem;
  font-weight: 400;
  font-size: 1rem;
  background: transparent;
  cursor: pointer;
}
.ymainhy .yhomey_but button:hover {
  border: 2px solid rgb(17 11 11);
}
.yhomey_but .shiactive {
  cursor: not-allowed;
}
.ymainbt .yhomey_but button {
  color: #f7f7f8bf;
  box-shadow: inset 0 0 0 2px #f7f7f8bf;
}
.ymainbt .yhomey_but button:hover {
  background: #f7f7f8bf;
  box-shadow: none;
  color: #272e35;
}
.ymainhy .car_txt {
  color: #000;
}
.yhomey_inpbox {
  width: 100%;
  justify-content: center;
  column-gap: 0.5rem;
  margin-bottom: 2rem;
}
.yhomeyinpy {
  width: 3.125rem;
  height: 3.875rem;
}
.yhomeyinpy > input {
  font-family: "Poppins";
  width: 100%;
  height: 100%;
  padding: 0.625rem;
  border: 1px solid rgb(179 187 202);
  transition: all 0.15s;
  color: white;
  box-sizing: border-box;
  background: transparent;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 1.2px;
  font-weight: 400;
  border-radius: 0.9375rem;
  text-align: center;
}
.ymainhy .yhomeyinpy > input {
  border-color: rgb(105 111 122);
  color: black;
}
.yhomeyinpy > input:focus {
  border-color: white;
}
.ymainhy .yhomeyinpy > input:focus {
  border-color: rgb(56 59 64);
}
.ymainhy .yhomey_two {
  color: #000;
}

.ymainhy .yhomey_four {
  color: #000;
}

.yhomey_one {
  width: 100%;
}

.yhomey_two {
  width: 100%;
  text-align: center;
  font-family: "Inter";
  margin-top: 1rem;
  margin-bottom: 1.5rem;
  font-size: 20px;
  font-weight: 400;
  line-height: 1.2;
  color: #6e757c;
}

.ymainhy .yhomey_three {
  color: #000;
}

.ymainhy .yhome_six {
  color: #000;
}

.ymainhy .yhome_five {
  color: #000;
  border-color: #696f7a;
}

.ymainhy .yhome_five:hover {
  background-color: #000;
  color: white;
}

.yhomey_three {
  font-family: "Poppins";
  font-size: 72px;
  line-height: 1.1111111111;
  text-align: center;
  color: white;
}

.yhomey_four {
  font-family: "Inter";
  font-size: 20px;
  font-weight: 400;
  line-height: 1.2;
  color: #6e757c;
  width: 75%;
  margin: 1.5rem auto;
  text-align: center;
  color: #6e757c;
}

.yhome_five {
  font-size: 18px;
  text-align: center;
  margin: 1rem auto;
  width: 10rem;
  color: white;
  font-family: "Inter";
  border-radius: 10px;
  padding: 1rem 2.5rem;
  border: 1px white solid;
}

.yhome_five:hover {
  background-color: white;
  color: #000;
  cursor: pointer;
  transition: background-color 0.5s, color 0.5s;
}

.yhome_six {
  margin: 2rem 0 2rem 0;
  color: #b3bbca;
  font-size: 22px;
  text-align: center;
  font-family: "Inter";
}

.app_one {
  width: 100%;
  height: 100%;
  background-size: 100%;
  background-repeat: no-repeat;
  overflow: hidden;
  font-family: "Poppins" !important;
}

.ymainhy .app_five {
  color: black;
}

.ymainhy .app_five > p {
  color: rgb(111 198 81);
}
@media screen and (max-width: 1200px) {
  .someAi {
    width: 100%;
  }

  .some_one > h2 {
    font-size: 2.75rem;
    line-height: 3rem;
  }

  .some_one > p {
    width: 100%;
  }

  .carousel-container {
    margin-left: 0rem;
  }

  .carousel-card {
    width: 330px;
    height: 350px;
    /* width: 100%; */
  }

  .carousel-card:nth-child(1) {
    margin-left: 1.4rem;
  }
  .carousel-card:nth-child(2) {
    margin-left: 5.3rem;
  }

  .carousel-card:nth-child(3) {
    margin-left: 5.5rem;
  }

  .carousel-card:nth-child(4) {
    margin-left: 5.4rem;
  }

  .some_two {
    margin-top: 8rem;
  }

  .car_txtx {
    text-align: center;
  }

  .yhomey_two {
    font-size: 1rem;
    line-height: 1.5rem;
    margin-bottom: 1rem;
  }

  .yhomey_three {
    font-size: 2.5rem;
    line-height: 3rem;
    margin-bottom: 1.25rem;
  }

  .yhomey_four {
    width: 100%;
    font-size: 1rem;
    line-height: 1.5rem;
    margin: 0 0 1rem;
  }

  .yhome_five {
    width: 8rem;
    font-size: 14px;
    padding: 1rem;
  }

  .yhome_six {
    font-size: 0.75rem;
  }

  .ybiao_one {
    width: 100%;
    margin: 0;
    padding: 0;
    flex-direction: column;
  }

  .ybiao_one {
    width: 100%;
    margin: 0;
    padding: 0;
    flex-direction: column;
  }

  .ytwobox > h2 {
    font-size: 2.75rem;
    padding-top: 4.5rem;
    margin-bottom: 2.5rem;
  }

  .ybiao > h2 {
    font-size: 2.75rem;
    padding-top: 4.5rem;
    margin-bottom: 2.5rem;
  }

  .sju > h2 {
    font-size: 2.75rem;
    padding-top: 4.5rem;
    margin-bottom: 2.5rem;
  }

  .ytwo {
    width: 100%;
    display: block;
    padding: 2rem;
  }

  .ybiao_two {
    width: 100%;
    display: flex;
    align-items: center;
    margin: 2rem 0;
  }

  .ybiao_two > p {
    font-size: 1.15rem;
    text-align: center;
    padding: 0.5rem 0;
    margin: 0;
  }

  .ybiao_five {
    margin-top: 1rem;
  }

  .ybiao_right {
    width: 100%;
    height: auto;
  }

  #chart {
    width: 100%;
    display: flex;
    justify-content: center;
  }
}
</style>
