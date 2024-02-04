<template>
  <div class="yward">
    <div class="ywardbox flex jus">
      <div class="ywardbf flex">
        <div class="ywardbfcon">
          <h2 class="ywardbfctit flex">
            <img src="../assets/gift.png" alt="" /> <span>My Rewards</span>
          </h2>
          <div class="ywardbfl flex">
            <div class="ywardbfly flex">
              <div class="money">
                <img
                  src="data:image/png;base64,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"
                  alt=""
                />
              </div>
              <div class="moneytxt flex flexcol">
                <div>{{ Commissions }}</div>
                <span>Commissions</span>
              </div>
            </div>
            <div class="ywardbflt flex">
              <div class="points">
                <img
                  src="data:image/png;base64,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"
                  alt=""
                />
              </div>
              <div class="moneytxt flex flexcol">
                <div>{{ points }}</div>
                <span>Points</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="ywardbfcr">
        <h2 class="ywardbfctit flex">
          <img src="../assets/user.png" alt="" /> <span>My Referrals</span>
        </h2>
        <div class="ywardbfcrbox">
          <div class="ywardbfcrbc">
            <div class="ywardbfcrbctop flex">
              <div>Refer and get rewards</div>
              <button>Connect to Get starteded</button>
            </div>
            <p>
              Join the referral program and get rewards for transfers made from
              your unique referral link.
            </p>
            <div class="link-box">
              <a href="" target="_blank" class="link-item">
                <img
                  src="https://owlto.finance/assets/twitter-66225175.png"
                  alt="link"
                />
              </a>
              <a href="" target="_blank" class="link-item">
                <img
                  src="https://owlto.finance/assets/telegram-96270d36.jpg"
                  alt="link"
                />
              </a>
              <a href="" target="_blank" class="link-item">
                <img
                  src="https://owlto.finance/assets/whatsapp-78286f95.jpg"
                  alt="link"
                />
              </a>
              <a href="" target="_blank" class="link-item">
                <img
                  src="https://owlto.finance/assets/facebook-e3fcdba3.jpg"
                  alt="link"
                />
              </a>
              <a href="" target="_blank" class="link-item">
                <img
                  src="https://owlto.finance/assets/line-f9910d12.png"
                  alt="link"
                />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="ywardlea">
      <h2 class="ywardbfctit flex">
        <img src="../assets/jb.png" alt="" />
        <span>LeaderBoard</span>
      </h2>
      <div class="ywardleaf flex jus">
        <div class="ywardleafl">
          <h2 class="ywardbfctit flex">
            <span>Commissions</span>
          </h2>
          <div class="ywardleafltxt">
            <div class="th">
              <div class="th_item">Rank</div>
              <div class="th_item">Address</div>
              <div class="th_item">Totals</div>
            </div>
            <div class="scrool">
              <div
                v-for="(item, index) in huanlist"
                :key="index"
                class="leftls flex"
              >
                <div class="leftlsl">
                  <img
                    :class="item.url == '' ? 'leftlslnone' : 'leftlslb'"
                    :src="item.url"
                    alt=""
                  />
                  <span
                    :class="item.url != '' ? 'leftlslnone' : 'leftlsltxt'"
                    >{{ item.rank }}</span
                  >
                </div>
                <div class="leftlsc">
                  {{
                    item.address.substring(0, 4) +
                    "..." +
                    item.address.substring(
                      item.address.length - 4,
                      item.address.length
                    )
                  }}
                </div>
                <div class="leftlsr">{{ item.totals }} ETH</div>
              </div>
            </div>
          </div>
        </div>
        <div class="ywardleafl">
          <h2 class="ywardbfctit flex">
            <span>Points</span>
          </h2>
          <div class="ywardleafltxt">
            <div class="th">
              <div class="th_item">Rank</div>
              <div class="th_item">Address</div>
              <div class="th_item">Totals</div>
            </div>
            <div class="scrool">
              <div
                v-for="(item, index) in leadlist"
                :key="index"
                class="leftls flex"
              >
                <div class="leftlsl">
                  <img
                    :class="item.url == '' ? 'leftlslnone' : 'leftlsllead'"
                    :src="item.url"
                    alt=""
                  />
                  <span
                    :class="item.url != '' ? 'leftlslnone' : 'leftlsltxt'"
                    >{{ item.rank }}</span
                  >
                </div>
                <div class="leftlsc">
                  {{
                    item.address.substring(0, 4) +
                    "..." +
                    item.address.substring(
                      item.address.length - 4,
                      item.address.length
                    )
                  }}
                </div>
                <div class="leftlsr">{{ item.totals }}</div>
              </div>
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
let Commissions = ref("—");
let points = ref("—");
let leadlist = ref([
  {
    rank: "1",
    url: "https://owlto.finance/assets/p1-1b6bec58.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
]);
let huanlist = ref([
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
  {
    rank: "1",
    url: "https://owlto.finance/assets/c1-df62b591.png",
    address: "0xF8EA74CCEDd1112a2deeB39F95891c78F89F9bE0",
    totals: "0.111",
  },
]);
let valqh = ref(0);
let reglist = ref([]);
onMounted(() => {
  // api
  //   .toppoint({
  //     appId: "xbot",
  //   })
  //   .then((res) => {
  //     leadlist.value = res.data.data.topPointList;
  //   })
  //   .catch((err) => {
  //     console.log(err);
  //   });
  // api
  //   .registers({
  //     appId: "xbot",
  //   })
  //   .then((res) => {
  //     console.log("registers", res.data.data.userRegisterList);
  //     huanlist.value = res.data.data.userRegisterList;
  //   })
  //   .catch((err) => {
  //     console.log(err);
  //   });
});
</script>

<style scoped>
.yward {
  width: 100%;
  height: auto;
  padding-top: 10.5rem;
  background: rgb(30, 37, 43);
}
.ymainhy .yward {
  background: white;
}
.ywardbox {
  width: 60%;
  margin: 0 auto;
}
.ywardbf {
  width: 37.573%;
  align-content: flex-end;
}
.ywardbfcon {
  width: 100%;
}
.ywardbfl {
  width: 100%;
  height: auto;
  padding: 1rem 1.5rem 1rem 1rem;
  text-align: center;
  position: relative;
  column-gap: 1.5rem;
  border-radius: 1.5rem;
  overflow: hidden;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
  box-sizing: border-box;
}
.ymainhy .ywardbfl {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
}
.ymainhy .moneytxt > div {
  color: #000;
}
.ymainhy .ywardbfcrbox {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
}
.ymainhy .ywardbfcrbctop > div {
  border-color: rgb(56, 56, 56);
  color: #000;
}
.ymainhy .ywardbfcrbctop > button {
  color: #000;
}
.ywardbfl::before {
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
.ywardbfly {
  width: 46.887%;
  align-items: center;
}
.money {
  width: 5.0625rem;
  height: 4.4375rem;
  padding: 0 1.25rem 0.625rem 0;
  box-sizing: border-box;
}
.money > img {
  width: 100%;
}
.moneytxt {
  gap: 0.3rem;
}
.moneytxt > div {
  font-family: "Poppins";
  font-size: 1.5rem;
  line-height: 1.25rem;
  color: white;
  text-align: left;
}
.moneytxt > span {
  font-family: "Interl";
  font-size: 1rem;
  line-height: 1.5rem;
  color: #6e757c;
}
.ywardbflt {
  width: 42.607%;
  align-items: center;
}
.points {
  width: 6.75rem;
  height: 5rem;
  padding: 0 0.625rem 0.625rem 2.25rem;
  box-sizing: border-box;
}
.points > img {
  width: 100%;
}
.ywardbfctit {
  align-items: center;
  column-gap: 0.5rem;
  color: #fff;
  font-size: 30px;
  line-height: 36px;
  font-weight: 600;
  font-family: "Poppins";
  margin-bottom: 1.5rem;
}
.ymainhy .ywardbfctit {
  color: #000;
}
.ywardbfctit > img {
  width: 1.3rem;
  height: 1.3rem;
}
.ywardbfcr {
  width: 59.74%;
}
.ywardbfcrbox {
  width: 100%;
  padding: 1.2rem 1.5rem;
  position: relative;
  border-radius: 1.5rem;
  overflow: hidden;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
  box-sizing: border-box;
}
.ywardbfcrbox::before {
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
.ywardbfcrbox::after {
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
.ywardbfcrbc {
  width: 100%;
  padding: 0.5rem 0;
}
.ywardbfcrbctop {
  align-items: center;
  column-gap: 1.2rem;
}
.ywardbfcrbctop > div {
  font-family: "Interl";
  height: 2rem;
  font-size: 1rem;
  line-height: 2rem;
  padding-left: 0.5rem;
  padding-right: 1.5rem;
  user-select: auto;
  white-space: nowrap;
  border: 0.05rem solid rgba(226, 226, 226, 0.2);
  box-shadow: 0 0.5rem 1.8rem #0000;
  border-radius: 0.2rem;
  color: white;
}
.ywardbfcrbctop > button {
  font-family: "Interl";
  padding: 0.2rem 0.8rem;
  border: none;
  font-size: 1rem;
  background-image: linear-gradient(to right, #f5c539, #f39800);
  border-radius: 0.2rem;
  height: 2rem;
  cursor: pointer;
  color: white;
}
.ywardbfcrbctop > button:hover {
  background-image: linear-gradient(to right, #f39800, #f5c539);
}
.ywardbfcrbc > p {
  font-family: "Interl";
  font-size: 1.25rem;
  line-height: 2rem;
  margin: 1.5rem 0 1rem;
  color: #6e757c;
}
.link-box {
  width: 100%;
  display: flex;
  gap: 1.5rem;
  align-items: center;
  padding: 0.5rem 0 0 0.5rem;
  box-sizing: border-box;
  position: relative;
  z-index: 10;
}
.link-item {
  width: 2rem;
  height: 2rem;
  border-radius: 50%;
}
.link-item > img {
  width: 100%;
  border-radius: 50%;
  cursor: pointer;
}
.ywardlea {
  width: 60%;
  margin: 3rem auto 0;
}
.ywardleaf {
  column-gap: 2rem;
}
.ywardleafl {
  flex: 1;
}
.ywardleafltxt {
  height: 24.6rem;
  padding: 1.2rem;
  box-sizing: border-box;
  border-radius: 1.5rem;
  position: relative;
  overflow: hidden;
  background: rgb(40, 48, 54);
  box-shadow: 0 8px 32px #0000001a;
}
.ymainhy .ywardleafltxt {
  box-shadow: 0 8px 32px #0000001a;
  background: #f7f7f8;
}
.ywardleafltxt::before {
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
.ywardleafltxt::after {
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
.th {
  width: 100%;
  height: 2.7rem;
  line-height: 2.7rem;
  display: flex;
  overflow: hidden;
  border-radius: 0.5rem;
  background-color: #181818;
  font-size: 1.2rem;
  font-weight: 450;
  position: relative;
  z-index: 10;
}
.th_item {
  font-family: "Poppins";
  flex: 1;
  text-align: center;
  color: white;
  font-size: 1.2rem;
  line-height: 2.7rem;
}
.ymainhy .th {
  background: white;
}
.ymainhy .th_item {
  color: #000;
}
.ymainhy .leftlsc {
  color: #000;
}
.ymainhy .leftlsr {
  color: #000;
}
.scrool {
  height: 19.5rem;
  overflow: auto;
  position: relative;
  z-index: 10;
}

.scrool::-webkit-scrollbar {
  width: 8px;
}

.scrool::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.2);
  box-shadow: inset 0 0 5px rgba(255, 255, 255, 0.2);
}
.ymainhy .scrool::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background: rgba(0, 0, 0, 0.2);
  box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
}

.scrool::-webkit-scrollbar-corner {
  border-radius: 0;
  background: rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
  -webkit-box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
}
.scrool > div:nth-child(odd) {
  background: transparent;
}
.scrool > div:nth-child(even) {
  background: rgb(50, 50, 50);
}
.scrool > div:hover {
  background: #53514e;
}
.ymainhy .scrool > div:nth-child(even) {
  background: rgb(125, 125, 125);
}
.ymainhy .scrool > div:hover {
  background: rgb(100, 100, 100);
}
.leftls {
  width: 100%;
  height: 3.1rem;
  font-size: 0.9rem;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.leftlsl {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}
.leftlslnone {
  display: none;
}
.leftlslb {
  width: 1.9375rem;
  height: 1.9375rem;
}
.leftlsc {
  flex: 1;
  font-family: "Interl";
  font-size: 1.125rem;
  line-height: 1.8125rem;
  color: white;
  text-align: center;
}
.leftlsr {
  flex: 1;
  font-family: "Interl";
  font-size: 1.125rem;
  line-height: 1.8125rem;
  color: white;
  text-align: center;
}
.leftlsltxt {
  flex: 1;
  font-family: "Interl";
  font-size: 1.125rem;
  line-height: 1.8125rem;
  color: white;
  text-align: center;
}
.leftlsllead {
  width: 1.8125rem;
  height: 2.125rem;
}
@media (max-width: 1250px) {
  .ywardbfcon {
    margin-bottom: 1.5rem;
  }
  .yward {
    padding-top: 6.5rem;
  }
  .ywardbox {
    width: 95%;
    display: block;
  }
  .ywardbf {
    width: 100%;
  }
  .ywardbfcr {
    width: 100%;
  }
  .ywardbfcrbctop {
    display: block;
  }
  .ywardbfcrbctop > div {
    width: 100%;
    text-align: center;
    box-sizing: border-box;
    margin-bottom: 0.75rem;
  }
  .ywardbfcrbctop > button {
    width: 100%;
    text-align: center;
    box-sizing: border-box;
  }
  .link-box {
    padding: 0.5rem 0.5rem 0 0.5rem;
    justify-content: center;
  }
  .ywardbfcrbc > p {
    text-align: center;
  }
  .ywardlea {
    width: 95%;
  }
  .ywardleaf {
    display: block;
  }
  .ywardleafl {
    padding-bottom: 1.5rem;
  }
  .leftlslb {
    width: 1.5rem;
    height: 1.5rem;
  }
  .th_item {
    font-size: 1rem;
  }
  .leftlsc {
    font-size: 0.875rem;
  }
  .leftlsr {
    font-size: 0.875rem;
  }
  .leftlsllead {
    width: 1.5rem;
    height: 1.8rem;
  }
}
</style>
