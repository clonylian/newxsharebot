<template>
  <div class="yleadtop">
    <h2>Supply Reward</h2>
    <div class="yleadtbox flex">
      <div class="yleadbtcon">
        <h4>$304.06K</h4>
        <p>This Week's Rewards</p>
      </div>
      <div class="yleadbtcon">
        <h4>$0</h4>
        <p>Available to claim</p>
      </div>
      <div class="yleadbtcon yleadbtcons">
        <h4>$79.54K</h4>
        <p>Total Rewards Distributed</p>
      </div>
    </div>
  </div>
  <div class="yleader flex jus">
    <div class="yleaderleft">
      <div class="yleaderltop flex jus">
        <h1>{{ $store.state.txt.yleadertitle }}</h1>
        <span>{{ $store.state.txt.yleadercont }}</span>
      </div>
      <div class="yleaderlcon">
        <div class="yleaderlctxt">
          <div class="yleaderlcb flex">
            <div style="width: 13.71%">{{ $store.state.txt.yleadertaby }}</div>
            <div style="width: 44.231%">{{ $store.state.txt.yleadertabt }}</div>
            <div style="width: 25.2747%">
              {{ $store.state.txt.yleadertabthr }}
            </div>
            <div style="width: 16.7842%; text-align: right">
              {{ $store.state.txt.yleadertabf }}
            </div>
          </div>
          <div class="yleaderlct">
            <div
              v-for="(item, i) in leadlist"
              :key="i"
              class="yleaderlcttiao flex"
            >
              <div style="width: 13.71%" class="yleaderlctty">
                <span>{{ item.rankingNum }}</span>
              </div>
              <div style="width: 44.231%" class="yleaderlcttt flex">
                <div>
                  <img
                    :class="item.userImg == null ? 'yleaderjolnone' : ''"
                    :src="item.userImg"
                    alt=""
                  />
                </div>
                <div>{{ item.userName }}</div>
              </div>
              <div style="width: 25.2747%" class="yleaderlcttthr">
                {{ item.invited == null ? "-" : item.invited }}
              </div>
              <div
                style="width: 16.7842%; text-align: right"
                class="yleaderlcttf"
              >
                {{ parseFloat(item.totalPoint).toFixed(0) }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="yleadercenterg"></div>
    <div class="yleaderright">
      <h2>{{ $store.state.txt.yleadersamletitle }}</h2>
      <div class="yleaderrcon">
        <div
          class="yleaderjoins flex jus"
          v-for="(item, i) in huanlist"
          :key="i"
        >
          <div class="yleaderjoleft">
            <img
              :class="item.userImg == null ? 'yleaderjolnone' : ''"
              :src="item.userImg"
              alt=""
            />
          </div>
          <div class="yleaderjoright">
            <div class="yleaderjrt flex jus">
              <div>{{ item.userName }}</div>
              <span
                >{{
                  Math.floor(
                    (new Date().getTime() - Date.parse(item.registerTime)) /
                      60000
                  )
                }}
                minutes age</span
              >
            </div>
            <div class="yleaderjtb">
              Invited by {{ item.invited.substring(0, 8) + "..." }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import api from "../common/api";
import Axios from "axios";
let regtime = ref("2023-11-28 11:11:11");
let leadlist = ref([]);
let huanlist = ref([]);
let valqh = ref(0);
let reglist = ref([]);
onMounted(() => {
  api
    .toppoint({
      appId: "xbot",
    })
    .then((res) => {
      leadlist.value = res.data.data.topPointList;
    });
  api
    .registers({
      appId: "xbot",
    })
    .then((res) => {
      console.log("registers", res.data.data.userRegisterList);
      huanlist.value = res.data.data.userRegisterList;
    });
});
</script>

<style scoped>
.yleader {
  width: 100%;
  padding: 3.5rem 4rem;
  box-sizing: border-box;
  background: rgb(30, 37, 43);
  /* align-items: center; */
}
.yleadtop {
  width: 100%;
  padding: 8.5rem 4rem 0;
  background: rgb(30, 37, 43);
  box-sizing: border-box;
}
.yleadtop > h2 {
  display: inline-block;
  color: #fff;
  font-size: 48px;
  line-height: 56px;
  font-weight: 600;
  font-family: "Poppins";
  padding: 1rem 0;
  border-bottom: 3px solid rgb(255 110 48);
  margin-bottom: 3rem;
}
.yleaderlcttiao {
  align-items: center;
}
.yleadtbox {
  width: 100%;
  align-items: center;
  column-gap: 1.5rem;
}
.yleadbtcon {
  width: 25%;
  padding: 2.75rem 1.875rem;
  border: 1px solid #323338;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
  border-radius: 1rem;
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}
.yleadbtcon::before {
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
  width: 80px;
  height: 80px;
  filter: blur(160px);
  opacity: 0.6;
}
.yleadbtcon::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(
    135.15deg,
    #ae80dc 1.17%,
    #dc83c3 31.88%,
    #8084dc 65.46%
  );
  top: -280px;
  left: -280px;
  width: 560px;
  height: 560px;
  opacity: 0.6;
  filter: blur(278.261px);
}
.yleadbtcon > h4 {
  color: #fff;
  font-size: 2rem;
  line-height: 2.5rem;
  font-weight: 600;
  font-family: "Poppins";
  margin-bottom: 0.75rem;
  position: relative;
  z-index: 10;
}
.yleadbtcon > p {
  display: block;
  font-family: "Inter";
  color: #9999a7;
  font-weight: 500;
  line-height: 18px;
  margin-top: 4px;
  font-size: 1.5rem;
  position: relative;
  z-index: 10;
}
.yleaderlctty {
  padding: 0.5rem 1rem 0.5rem 0;
  box-sizing: border-box;
}
.yleaderlctty > span {
  font-family: "GT Pressura Bold";
  background: rgb(17 20 12);
  text-align: center;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 400;
  padding: 0.5rem 1rem;
  display: block;
  color: rgb(179 187 202);
}
.yleaderlcttt {
  font-family: "Inter";
  align-items: center;
  gap: 2rem;
  padding: 0.5rem 1rem;
  box-sizing: border-box;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 400;
  color: rgb(179 187 202);
}
.yleaderlcttt > div:nth-child(1) {
  width: 2rem;
  height: 2rem;
  overflow: hidden;
  border-radius: 50%;
  background: rgb(179 187 202);
}
.yleaderlcttt > div:nth-child(1) > img {
  width: 100%;
  height: 100%;
}
.yleaderlcttthr {
  font-family: "Inter";
  padding: 0.5rem 1rem;
  box-sizing: border-box;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 400;
  color: rgb(179 187 202);
}
.yleaderlcttf {
  font-family: "Inter";
  padding: 0.5rem 1rem;
  box-sizing: border-box;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 400;
  color: rgb(179 187 202);
}
.ymainhy .yleader {
  background: white;
  /* background: url("../assets/homebgw.png"); */
}
.ymainhy .yleadtop {
  background: white;
  /* background: url("../assets/homebgw.png"); */
}
.ymainhy .yleadtop > h2 {
  color: #000;
}
.ymainhy .yleadbtcon {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
  border-color: transparent;
}
.ymainhy .yleadbtcon > h4 {
  color: #000;
}
.ymainhy .yleadbtcon > p {
  color: #6e757c;
}
.ymainhy .yleaderleft {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
  border-color: transparent;
}
.ymainhy .yleaderltop > h1 {
  color: #000;
}
.ymainhy .yleaderright {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
  border-color: transparent;
}
.yleaderleft {
  width: 78.4047%;
  padding: 2rem;
  border-radius: 1.5rem;
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
}
.yleaderleft::before {
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
.yleaderleft::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(
    135.15deg,
    #ae80dc 1.17%,
    #dc83c3 31.88%,
    #8084dc 65.46%
  );
  top: -280px;
  left: -280px;
  width: 560px;
  height: 560px;
  opacity: 0.6;
  filter: blur(278.261px);
}

.yleaderltop {
  width: 100%;
  align-items: center;
  color: #fff;
}
.ymainhy .yleaderltop {
  color: rgb(56 59 64) !important;
}
.yleaderltop > h1 {
  font-family: "Poppins";
  font-size: 48px;
  line-height: 56px;
  letter-spacing: 0;
  font-weight: 600;
}
.yleaderltop > span {
  color: #6e757c;
  font-family: "Inter";
  font-size: 16px;
  font-weight: 500;
  line-height: 24px;
}
.yleaderlcon {
  width: 100%;
  max-height: 70vh;
  margin-top: 2rem;
}
.yleaderlctxt {
  width: 100%;
  height: auto;
}
.yleaderlct {
  width: 100%;
  max-height: 54vh;
  overflow-y: scroll;
}
::-webkit-scrollbar {
  display: none;
}
.yleaderlcb {
  width: 100%;
  border-top: 1px solid rgb(117 131 93);
  border-bottom: 1px solid rgb(117 131 93);
}
.ymainhy .yleaderlcb > div {
  color: rgb(105 111 122);
}
.ymainhy .yleaderlcttiao > div {
  color: rgb(105 111 122);
}
.ymainhy .yleaderlctty > span {
  color: rgb(105 111 122);
  background: #fff;
}
.yleaderlcb > div {
  font-family: "Inter";
  font-size: 1rem;
  line-height: 1.5rem;
  letter-spacing: 1.6px;
  font-weight: bold;
  padding: 0.5rem 1rem;
  color: rgb(179 187 202);
  box-sizing: border-box;
}
.yleadercenterg {
  height: 70vh;
  width: 1px;
  border-left: 1px solid rgb(179 187 202);
}
.yleaderright {
  width: 19%;
  padding: 1.5rem 1rem;
  border-radius: 1.5rem;
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
}
.yleaderright::before {
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
.yleaderright::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(
    135.15deg,
    #ae80dc 1.17%,
    #dc83c3 31.88%,
    #8084dc 65.46%
  );
  top: -280px;
  left: -280px;
  width: 560px;
  height: 560px;
  opacity: 0.6;
  filter: blur(278.261px);
}
.yleaderright > h2 {
  font-family: "Poppins";
  height: 3.375rem;
  margin: 0.5rem 0 1.375rem;
  font-size: 1.5rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 600;
  color: rgb(179 187 202);
}
.ymainhy .yleaderright > h2 {
  color: #000;
}
.ymainhy .yleaderjrt > div {
  color: rgb(17, 11, 11);
}
.ymainhy .yleaderjrt > span {
  color: rgb(105 111 122);
}
.ymainhy .yleaderjtb {
  color: rgb(105 111 122);
}
.ymainhy .yleaderlcttt > div:nth-child(1) {
  background: rgb(105 111 122);
}
.ymainhy .yleaderjoleft {
  background: rgb(105 111 122);
}
.yleaderrcon {
  width: 100%;
  max-height: 60vh;
  border-top: 1px solid rgb(179 187 202);
  padding-top: 1.5rem;
  box-sizing: border-box;
  overflow-y: scroll;
  position: relative;
  z-index: 10;
}
.yleaderjoins {
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
  /* animation-duration: 3s;
  animation-name: enter-fade;
  animation-iteration-count: infinite; */
  opacity: 1;
}
@keyframes enter-fade {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.yleaderjoright {
  width: 84%;
}
.yleaderjrt {
  width: 100%;
  align-items: center;
}
.yleaderjrt > div {
  font-family: "Poppins";
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  width: 50%;
  font-size: 1rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 600;
  color: white;
}
.yleaderjrt > span {
  font-family: "Inter";
  font-size: 0.8125rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 500;
  color: rgb(179 187 202);
}
.yleaderjtb {
  font-family: "Inter";
  font-size: 0.8125rem;
  line-height: 160%;
  letter-spacing: 0;
  font-weight: 500;
  color: rgb(179 187 202);
}
.yleaderjoleft {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
  overflow: hidden;
  background: rgb(179 187 202);
}
.yleaderjolnone {
  display: none;
}
@media (max-width: 1250px) {
  .yleaderlcon {
    margin-top: 1rem;
  }
  .yleadtop {
    padding: 8.5rem 1rem 0;
  }
  .yleadtop > h2 {
    font-size: 2.5rem;
    line-height: 3rem;
  }
  .yleadtbox {
    display: block;
  }
  .yleadbtcon {
    width: 100%;
    padding: 2rem 1.5rem;
    margin-bottom: 1.25rem;
  }
  .yleadbtcons {
    margin: 0;
  }
  .yleadbtcon > h4 {
    font-size: 1.75rem;
    line-height: 2rem;
  }
  .yleaderltop > h1 {
    font-size: 2.5rem;
    line-height: 3rem;
  }
  .yleadbtcon > p {
    font-size: 1.25rem;
    line-height: 1.5rem;
  }
  .yleader {
    padding: 8.5rem 1rem 3.5rem;
    display: block;
  }
  .yleaderltop {
    display: block;
    text-align: center;
  }
  .yleaderleft {
    padding: 1rem 0.5rem;
    width: 100%;
    margin-bottom: 1.5rem;
  }
  .yleaderlctxt {
    width: 100%;
  }
  .yleaderlct {
    width: 100%;
  }
  .yleadercenterg {
    display: none;
  }
  .yleaderlcttt {
    font-size: 0.75rem;
  }
  .yleaderlcttthr {
    width: 27.2747% !important;
    font-size: 0.75rem;
    padding: 0.5rem 0;
  }
  .yleaderlcb div {
    font-size: 0.75rem;
    padding: 0.5rem 0;
  }
  .yleaderlcb div:nth-child(3) {
    width: 27.2747% !important;
  }
  .yleaderlctty > span {
    padding: 0.25rem 0;
  }
  .yleaderlctty {
    padding: 0.5rem 0;
  }
  .yleaderlcttt {
    width: 40% !important;
    padding: 0.25rem;
    gap: 0.5rem;
  }
  .yleaderlcttt > div:nth-child(1) {
    width: 1rem;
    height: 1rem;
  }
  .yleaderlcttf {
    font-size: 0.75rem;
    padding: 0.5rem 0;
  }
  .yleaderlcb > div:nth-child(2) {
    width: 40% !important;
  }
  .yleaderright {
    width: 100%;
    padding: 1rem 0.75rem;
  }
  .yleaderright > h2 {
    height: 2rem;
  }
  .yleaderjoins {
    width: 97.5%;
    margin: 0 auto 1rem;
    gap: 0.5rem;
  }
  .yleaderjoleft {
    width: 2rem;
    height: 2rem;
  }
  .yleaderjoright {
    width: 85%;
  }
}
@media (min-width: 1251px) and (max-width: 1900px) {
  .yleaderleft {
    width: 71%;
  }
  .yleaderright {
    width: 28%;
  }
  .yleaderjoins {
    justify-content: normal !important;
  }
}
</style>
