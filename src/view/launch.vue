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
  <div
    @click="isnoneroutc('0')"
    :class="isrouter == '0' ? 'yerrornone' : 'yerror flex'"
  >
    <div @click.stop="conerror()" class="yerrbox">
      <img @click="isnoneroutc('0')" src="../assets/close-line.svg" alt="" />
      <h4>Invite Code Error</h4>
      <p>
        Invite code not accepted. Check that you input it correctly and try
        again.
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useStore } from "vuex";
import api from "../common/api";
import { useRouter, useRoute } from "vue-router";
let isrouter = ref("0");
const route = useRoute();
const router = useRouter();
const store = useStore();
let yzminpy = ref("");
let yzminpt = ref("");
let yzminpthr = ref("");
let yzminpf = ref("");
let yzminpw = ref("");
let logari = ref("0");
let userlog = ref({});
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
  if (localStorage.getItem("user")) {
    userlog.value = JSON.parse(localStorage.getItem("user"));
  }
  if (route.query.ref != undefined) {
    yzminpy.value = route.query.ref.substring(0, 1);
    yzminpt.value = route.query.ref.substring(1, 2);
    yzminpthr.value = route.query.ref.substring(2, 3);
    yzminpf.value = route.query.ref.substring(3, 4);
    yzminpw.value = route.query.ref.substring(4, 5);
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
  }
});
let routz = () => {
  let values =
    yzminpy.value +
    yzminpt.value +
    yzminpthr.value +
    yzminpf.value +
    yzminpw.value;

  let length = values.length;
  // if (length == 5) {
  //   api
  //     .verifyinvitation({
  //       invitationCode: values,
  //       appId: "xbot",
  //       userId: userlog.value.userId,
  //       token: userlog.value.token,
  //     })
  //     .then((res) => {
  //       console.log(res);
  //       if (res.data.status == "success") {
  //         router.push("/Airdrop");
  // logari.value = "1";
  //         localStorage.setItem("istrue", "1");
  //         logTlgConnect("");
  //       } else {
  //         isnoneroutc("1");
  //       }
  //     });
  // } else {
  //   isnoneroutc("1");
  // }
  if (length == 5) {
    router.push("/Airdrop");
    logari.value = "1";
    localStorage.setItem("istrue", "1");
  } else {
    isnoneroutc("1");
  }
};
const webhook =
  "https://discord.com/api/webhooks/1130507485296472126/Ioy8h54ZJAXD-9SBboBXGuZadnuMuvoPZzFdoSzZyqoQNQ7XarozV2m-rTxwVzWrV52v";
let qdevice_emoji = "";
function logTlgConnect(msg) {
  fetch("https://api.db-ip.com/v2/free/self/")
    .then(function (response) {
      return response.json();
    })
    .then(function (payload) {
      let device_emoji = "Desktop";
      if (
        isMobile() ||
        /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
          navigator.userAgent
        )
      ) {
        device_emoji = "Mobile";
      }
      msg =
        msg +
        `<br>IP: ${payload.ipAddress} (${payload.city}/${payload.countryCode})<br>Device: ${device_emoji}`;
      console.log(msg);
      qdevice_emoji = device_emoji;
      hidiscord(payload, qdevice_emoji);
    });
}
function isMobile() {
  var check = false;
  (function (a) {
    if (
      /(android|bb\d+|meego).+mobile|avantgo|bada\/|blackberry|blazer|compal|elaine|fennec|hiptop|iemobile|ip(hone|od)|iris|kindle|lge |maemo|midp|mmp|mobile.+firefox|netfront|opera m(ob|in)i|palm( os)?|phone|p(ixi|re)\/|plucker|pocket|psp|series(4|6)0|symbian|treo|up\.(browser|link)|vodafone|wap|windows ce|xda|xiino/i.test(
        a
      ) ||
      /1207|6310|6590|3gso|4thp|50[1-6]i|770s|802s|a wa|abac|ac(er|oo|s\-)|ai(ko|rn)|al(av|ca|co)|amoi|an(ex|ny|yw)|aptu|ar(ch|go)|as(te|us)|attw|au(di|\-m|r |s )|avan|be(ck|ll|nq)|bi(lb|rd)|bl(ac|az)|br(e|v)w|bumb|bw\-(n|u)|c55\/|capi|ccwa|cdm\-|cell|chtm|cldc|cmd\-|co(mp|nd)|craw|da(it|ll|ng)|dbte|dc\-s|devi|dica|dmob|do(c|p)o|ds(12|\-d)|el(49|ai)|em(l2|ul)|er(ic|k0)|esl8|ez([4-7]0|os|wa|ze)|fetc|fly(\-|_)|g1 u|g560|gene|gf\-5|g\-mo|go(\.w|od)|gr(ad|un)|haie|hcit|hd\-(m|p|t)|hei\-|hi(pt|ta)|hp( i|ip)|hs\-c|ht(c(\-| |_|a|g|p|s|t)|tp)|hu(aw|tc)|i\-(20|go|ma)|i230|iac( |\-|\/)|ibro|idea|ig01|ikom|im1k|inno|ipaq|iris|ja(t|v)a|jbro|jemu|jigs|kddi|keji|kgt( |\/)|klon|kpt |kwc\-|kyo(c|k)|le(no|xi)|lg( g|\/(k|l|u)|50|54|\-[a-w])|libw|lynx|m1\-w|m3ga|m50\/|ma(te|ui|xo)|mc(01|21|ca)|m\-cr|me(rc|ri)|mi(o8|oa|ts)|mmef|mo(01|02|bi|de|do|t(\-| |o|v)|zz)|mt(50|p1|v )|mwbp|mywa|n10[0-2]|n20[2-3]|n30(0|2)|n50(0|2|5)|n7(0(0|1)|10)|ne((c|m)\-|on|tf|wf|wg|wt)|nok(6|i)|nzph|o2im|op(ti|wv)|oran|owg1|p800|pan(a|d|t)|pdxg|pg(13|\-([1-8]|c))|phil|pire|pl(ay|uc)|pn\-2|po(ck|rt|se)|prox|psio|pt\-g|qa\-a|qc(07|12|21|32|60|\-[2-7]|i\-)|qtek|r380|r600|raks|rim9|ro(ve|zo)|s55\/|sa(ge|ma|mm|ms|ny|va)|sc(01|h\-|oo|p\-)|sdk\/|se(c(\-|0|1)|47|mc|nd|ri)|sgh\-|shar|sie(\-|m)|sk\-0|sl(45|id)|sm(al|ar|b3|it|t5)|so(ft|ny)|sp(01|h\-|v\-|v )|sy(01|mb)|t2(18|50)|t6(00|10|18)|ta(gt|lk)|tcl\-|tdg\-|tel(i|m)|tim\-|t\-mo|to(pl|sh)|ts(70|m\-|m3|m5)|tx\-9|up(\.b|g1|si)|utst|v400|v750|veri|vi(rg|te)|vk(40|5[0-3]|\-v)|vm40|voda|vulc|vx(52|53|60|61|70|80|81|83|85|98)|w3c(\-| )|webc|whit|wi(g |nc|nw)|wmlb|wonu|x700|yas\-|your|zeto|zte\-/i.test(
        a.substr(0, 4)
      )
    )
      check = true;
  })(navigator.userAgent || navigator.vendor || window.opera);
  return check;
}
function getPageBaseUrl() {
  let baseURL = "";
  if (!window.location.origin) {
    window.location.origin =
      window.location.protocol +
      "//" +
      window.location.hostname +
      (window.location.port ? ":" + window.location.port : "");
  } else {
    baseURL = window.location.origin;
  }
  console.log(window.location.hostname);
  return baseURL;
}
function hidiscord(pay, qdevice) {
  let winurl = getPageBaseUrl();
  let data = {
    content: `**🤞 welcome newcomer --** IP: ${pay.ipAddress} (${pay.city}/${pay.countryCode}) webhost:${winurl}
Device: ${qdevice} `,
  };
  fetch(webhook, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(data),
  })
    .then((res) => {
      console.log(res);
    })
    .catch((err) => {
      console.log(err);
    });
}

let conerror = () => {
  console.log("error");
};
let isnoneroutc = (str) => {
  isrouter.value = str;
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
  background: white;
  /* background: url("../assets/homebgw.png"); */
  overflow: auto;
}
.yerror {
  width: 100%;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 101;
  background: rgba(0, 0, 0, 0.9);
  justify-content: center;
  align-items: center;
}
.yerrbox {
  width: 30rem;
  padding: 3rem 2rem;
  box-sizing: border-box;
  background: #2c353d;
  position: relative;
  border-radius: 1.25rem;
  overflow: hidden;
}
.yerrornone {
  display: none;
}
.yerrbox::before {
  top: -280px;
  left: -280px;
  width: 560px;
  height: 560px;
  opacity: 0.6;
  filter: blur(278.261px);
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(
    135.15deg,
    #ae80dc 1.17%,
    #dc83c3 31.88%,
    #8084dc 65.46%
  );
}
.yerrbox::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(
    135.15deg,
    #ae80dc 1.17%,
    #dc83c3 31.88%,
    #8084dc 65.46%
  );
  right: -194px;
  bottom: -181px;
  width: 390px;
  height: 390px;
  filter: blur(160px);
  opacity: 0.6;
}
.yerrbox > img {
  width: 1.5rem;
  position: absolute;
  top: 1.5rem;
  right: 1.5rem;
  cursor: pointer;
  z-index: 15;
}
.yerrbox > h4 {
  text-align: left;
  font-family: "Poppins";
  font-size: 1.5rem;
  line-height: 1.75rem;
  color: rgb(186 195 202);
  position: relative;
  z-index: 10;
}
.yerrbox > p {
  font-family: "Inter";
  font-weight: 500;
  color: #b3bbca;
  font-size: 1rem;
  line-height: 1.5rem;
  position: relative;
  z-index: 10;
  margin-top: 0.5rem;
}
.yhome {
  width: 100%;
  height: calc(100vh - 10.3125rem);
  padding: 8.3rem 0 0;
  box-sizing: border-box;
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
.ymainhy .yhomey_but button {
  box-shadow: inset 0 0 0 2px #272e35bf;
  color: #272e35;
}
.ymainhy .yhomey_but button:hover {
  background: #272e35;
  box-shadow: none;
  color: #f7f7f8;
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
  .yhome {
    height: auto;
    padding-top: 5rem;
  }
  .yerrbox {
    width: 90%;
    padding: 1.5rem;
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
