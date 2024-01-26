<template>
  <div :class="hybt == 0 ? 'ygg ymainbt' : 'ygg ymainhy'">
    <div class="fixtop">
      <div class="yhead">
        <div class="yheadbox flex jus">
          <div class="yheady flex">
            <router-link to="/">
              <img class="hyshowimg" src="./assets/blacklogo.png" alt=""
            /></router-link>
            <router-link to="/Leaderboard">
              {{ $store.state.txt.tabtwo }}</router-link
            >
          </div>
          <div class="yheads flex">
            <div class="yheadapps flex">
              <a href="" target="_blank">Docs</a>
              <a href="" target="_blank">Twitter</a>
              <a href="" target="_blank">Discord</a>
              <a href="" target="_blank">Telegram</a>
              <a href="" target="_blank">Medium</a>
            </div>
            <div class="qihuan" @click="hebtqh(1)">
              <svg
                class="btshow"
                width="16"
                height="16"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M8 11.75A3.75 3.75 0 1 0 4.25 8 3.765 3.765 0 0 0 8 11.75Zm0-6.5A2.75 2.75 0 1 1 5.25 8 2.765 2.765 0 0 1 8 5.25ZM8 2.958a.5.5 0 0 0 .5-.5V.5a.5.5 0 0 0-1 0v1.958a.5.5 0 0 0 .5.5ZM7.5 13.543V15.5a.5.5 0 1 0 1 0v-1.957a.5.5 0 0 0-1 0ZM3.728 4.432a.5.5 0 1 0 .707-.707L3.05 2.342a.5.5 0 1 0-.707.708l1.385 1.382ZM11.568 11.568a.503.503 0 0 0 0 .707l1.382 1.383a.5.5 0 1 0 .708-.708l-1.383-1.382a.501.501 0 0 0-.707 0ZM.5 8.5h1.958a.5.5 0 0 0 0-1H.5a.5.5 0 0 0 0 1ZM13.043 8a.5.5 0 0 0 .5.5h1.958a.5.5 0 1 0 0-1h-1.958a.5.5 0 0 0-.5.5ZM3.728 11.568 2.343 12.95a.501.501 0 0 0 .707.708l1.383-1.383a.5.5 0 1 0-.708-.707h.003Z"
                  fill="currentColor"
                  fill-opacity="0.87"
                ></path>
                <path
                  d="M11.92 4.58a.5.5 0 0 0 .352-.147l1.383-1.383a.5.5 0 0 0-.705-.707l-1.383 1.382a.5.5 0 0 0 .353.853v.002Z"
                  fill="currentColor"
                ></path>
              </svg>
              <svg
                class="hyshow"
                width="16"
                height="16"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M13.875 13.621A8.132 8.132 0 0 0 16 9.91a7.061 7.061 0 0 1-9.225-.655A7.05 7.05 0 0 1 6.146 0a8.053 8.053 0 0 0-3.765 2.13 8.123 8.123 0 0 0 0 11.491 8.132 8.132 0 0 0 11.494 0Z"
                  fill="currentColor"
                ></path>
              </svg>
            </div>
            <!-- <div class="lengqh">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="rgba(255,255,255,1)"
              >
                <path
                  d="M12 22C6.47715 22 2 17.5228 2 12C2 6.47715 6.47715 2 12 2C17.5228 2 22 6.47715 22 12C22 17.5228 17.5228 22 12 22ZM9.71002 19.6674C8.74743 17.6259 8.15732 15.3742 8.02731 13H4.06189C4.458 16.1765 6.71639 18.7747 9.71002 19.6674ZM10.0307 13C10.1811 15.4388 10.8778 17.7297 12 19.752C13.1222 17.7297 13.8189 15.4388 13.9693 13H10.0307ZM19.9381 13H15.9727C15.8427 15.3742 15.2526 17.6259 14.29 19.6674C17.2836 18.7747 19.542 16.1765 19.9381 13ZM4.06189 11H8.02731C8.15732 8.62577 8.74743 6.37407 9.71002 4.33256C6.71639 5.22533 4.458 7.8235 4.06189 11ZM10.0307 11H13.9693C13.8189 8.56122 13.1222 6.27025 12 4.24799C10.8778 6.27025 10.1811 8.56122 10.0307 11ZM14.29 4.33256C15.2526 6.37407 15.8427 8.62577 15.9727 11H19.9381C19.542 7.8235 17.2836 5.22533 14.29 4.33256Z"
                ></path>
              </svg>
              <div class="lengbox">
                <span></span>
                <div @click="changelang('en')">English</div>
                <div @click="changelang('ch')">中文</div>
              </div>
            </div> -->
            <div :class="$route.path == '/' ? 'yheadslau' : 'yheadslaunone'">
              <router-link to="/launch" target="_blank">
                Launch app</router-link
              >
            </div>
            <div :class="Twittername == '' ? 'twxnamenone' : 'twxname'">
              <svg
                version="1.1"
                id="Layer_1"
                xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink"
                x="0px"
                y="0px"
                width="570"
                height="568"
                viewBox="0 0 570 568"
                enable-background="new 0 0 570 568"
                xml:space="preserve"
              >
                <image
                  id="image0"
                  width="570"
                  height="568"
                  x="0"
                  y="0"
                  href="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wAARCAI4AjoDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD6pooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiuZ8f+I5vDGjw3lvBHM0k4h2yEgYKsc8f7tcB/wty/8A+gba/wDfbVcacpaoD2WivGv+FuX/AP0DbX/vtqP+FuX/AP0DbX/vtqfsZ9gPZaK8a/4W5f8A/QNtf++2o/4W5f8A/QNtf++2o9jPsB7LRXjX/C3L/wD6Btr/AN9tR/wty/8A+gba/wDfbUexn2A9lorxr/hbl/8A9A21/wC+2o/4W5f/APQNtf8AvtqPYz7Aey0V41/wty//AOgba/8AfbUf8Lcv/wDoG2v/AH21HsZ9gPZaK8a/4W5f/wDQNtf++2qSP4vXQP7zSYG/3ZiP6Gj2U+wHsNFeXWvxetGOLrSZ4/8ArnMH/mBW9YfEnw5dMFe4mtmPQTRH+a5FJ05LoB2dFVNP1Ky1GPfYXcFymM5ikDY+uKt1ABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFJgee/G//AJFS0/6/V/8ARcleH17h8b/+RUtP+v1f/RcleH12UPhAKKKK3AKKKKACiiigAooooAKKKKACiiigAooooAfBNJBIJIZHjkXoyNtI/EV2Gh/EfXtN2pcTC/gH8Nxy3/ffX881xlFKUVLcD3/w38RNG1hhDM/2G6P/ACznYbW+jdD+ODXZ18m11vhLx3qnh9kiZzd2I48iRvuj/ZPb+XtXPOh1iB9C0Vi+GfEuneIrXzbCX94ADJC/Dx/Uf1HFbVc7VtGAUUUUgCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAPPfjf8A8ipaf9fq/wDouSvD69w+N/8AyKlp/wBfq/8AouSvD666HwgFFFFbgFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQBZ02/utNvI7qxneCdDlXQ/p7j2r3PwB45t/EUa2t4Ug1RRynRZR6r/hXgdOhlkgmSaCRo5Y2DI6nBUjuKidNTWoH1hRXEfDjxmniG1+x3rouqQrlscCVf7w9/Uf5Hb1wyi4uzAKKKKQBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAee/G/8A5FS0/wCv1f8A0XJXh9e4fG//AJFS0/6/V/8ARcleH110PhAKKKK3AKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAnsLy40+9hu7SQxzwsGVh619H+DfEMPiTRY7yIBJh8s0QP3H9Pp3FfNNdV8OfEZ8Pa+jTNiyucRT56KOzfgT+RNZVoc0QPoiiiiuIAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAPPfjf/yKlp/1+r/6Lkrw+vcPjf8A8ipaf9fq/wDouSvD666HwgFFFFbgFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH0B8KtbOr+F4opW3XNl+4cnqV/hP5cfUGuyrwb4P6r9g8Vi2dsQ3sZjOem4cqf5j8a95rhqx5ZAFFFFZgFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAHnvxv/wCRUtP+v1f/AEXJXh9e4fG//kVLT/r9X/0XJXh9ddD4QCiiitwCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigCzpl21hqNtdx/fgkWQfUEGvqeNxIiuhyrAEH1FfJ9fTPgy4N14T0iZjlmtowx9wMH9RXNiFswNmiiiuYAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA89+N//ACKlp/1+r/6Lkrw+vcPjf/yKlp/1+r/6Lkrw+uuh8IBRRRW4BRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAV9FfDF9/gXST/sOPydhXzrX0Z8NY/K8D6Qv/TMt+bE/wBa58RsgOmooorlAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAPPfjf/AMip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mNT2pjUhDKaadTTQJjG6Uynt0plDGxppvanGm9qQDT0qNqkPSo2pCG19yfCfXD4i+HmiX7vvmMAhmJPJdCUYn6lc/jXw3X0/+yfqbXHhTWNOc5NreCVfZZF6fmjfnWcthxPcqKKKgsKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiikwPNvj3/yJ9n/ANf6f+i5K8Bavfvj3/yJ9n/1/p/6LkrwFq7sN8ADTTGp5qNq1ENNRt1p5pjdTSAQ9KjNSHpUZqQGmmNTzTGpgRGkPSlNIelT0AjPWkalPWkapYEZpjU80xqkQw02nGm0AMamNT2pjUhDKaadTTQJjG6Uynt0plDGxppvanGm9qQDT0qNqkPSo2pCG17r+yXdMviLxBaZ4ktY5f8AvlyP/Z68Kr2f9k8n/hPtVH8P9muT/wB/Y6h7Atz6qooorM0CiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooopMDzb49/8ifZ/wDX+n/ouSvAWr3749/8ifZ/9f6f+i5K8Bau7DfAA01G1PNMatWIYaYetPNMPWkAh6VGakPSozUgNNManmmNTAiNIelKaQ9KnoBGetI1KetI1SwIzTGp5pjVIhhptONNoAY1MantTGpCGU006mmgTGN0plPbpTKGNjTTe1ONN7UgGnpUbVIelRtSENr3L9ku3LeKddue0dmsf/fTg/8AsleG19L/ALJenNFoGvaiR8txdJApx/zzUk/+jKh7Atz3qiiiszQKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiikwPNvj3/AMifZ/8AX+n/AKLkrwFq9++Pf/In2f8A1/p/6LkrwFq7sN8ADWpjd6e1MbvWrEMNMPSnmmHpSAa3Q1GakboajNSA00xqeaY1MCNqaac1NNT0AjbrTXpzdaa9SwGGmmnGmmkBGabTjTaQhjUxqe1MakIZTTTqaaBMY3SmU9ulMoY2NNN7U403tSAaelRtUh6VG1IQ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iiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA//2Q=="
                ></image>
              </svg>

              <span>
                {{ Twittername }}
              </span>
            </div>
            <div class="yddhshow" @click="ydonshow(1)">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                <path
                  d="M8 4H21V6H8V4ZM3 3.5H6V6.5H3V3.5ZM3 10.5H6V13.5H3V10.5ZM3 17.5H6V20.5H3V17.5ZM8 11H21V13H8V11ZM8 18H21V20H8V18Z"
                ></path>
              </svg>
            </div>
          </div>
        </div>
      </div>
      <div class="yht flex">
        <a href="/Stake" class="flex"
          >1 svxai = 1.2457 XAI
          <span class="flex jiantl">
            <img src="./assets/lsj.svg" alt="" />0.02%
          </span>
        </a>
        <a href="/Stake" class="flex"
          >1 XAI = 0.074077 USD
          <span class="flex jiantl">
            <img src="./assets/lsj.svg" alt="" />0.25%
          </span>
        </a>
        <a href="/Stake" class="flex"
          >Staking APY: 8.05%
          <span class="flex jiantr">
            <img src="./assets/hxj.svg" alt="" />1.99%
          </span>
        </a>
      </div>
    </div>
    <div class="ymianbtbg">
      <div class="hidden md:block ybg"></div>
      <div class="hidden md:block ybg"></div>
    </div>
    <router-view></router-view>
    <Footer></Footer>
    <div
      :class="ydshow == 0 ? 'ydddh flex' : 'ydddh flex yddhshowy'"
      @click="ydonshow(0)"
    >
      <div class="ydddhl">
        <router-link to="/">{{ $store.state.txt.tabzero }}</router-link>
        <router-link to="/Leaderboard">{{
          $store.state.txt.tabtwo
        }}</router-link>
        <router-link to="/Ido">{{
          $store.state.txt.bxtttabthreetop
        }}</router-link>
      </div>
    </div>
  </div>

  <div :class="dhisshow == 0 ? 'dhshow flex' : 'dhshow flex dhhidd'">
    <div class="anidh flex">
      <img src="./assets/logos.png" alt="" />
      <span>Blex.Finance</span>
    </div>
  </div>
</template>
<script setup>
import hello from "hellojs/dist/hello.all";
import { onMounted, ref, onBeforeUnmount } from "vue";
import bus from "./utils/bus";
import { useStore } from "vuex";
import Web3Modal from "web3modal";
import { ethers } from "ethers";
import Footer from "./components/footer.vue";
const store = useStore();
let dhisshow = ref(0);
let googlegloin = ref(null);
let googlesignin = ref(null);
let showno = ref(0);
let hybt = ref(0);
let loginan = ref(0);
let Twittername = ref("");
const xhladdress = ref("");
const xxhladdress = ref("");
const xethbalance = ref("");
let ydshow = ref(0);
let ydonshow = (str) => {
  ydshow.value = str;
  console.log(ydshow.value == 1);
};
let changelang = (str) => {
  store.commit("changeyy", str);
};
let hebtqh = (str) => {
  if (hybt.value == str) {
    hybt.value = 0;
  } else {
    hybt.value = 1;
  }
};
let tcshow = async () => {
  showno.value = 1;
};
let qxdl = async () => {
  if (xhladdress.value != "") {
    web3Modal.clearCachedProvider();
  }
  loginan.value = 0;
  xxhladdress.value = "";
  Twittername.value = "";
  localStorage.clear();
  bus.$emit("qbbalance", "0.00");
};
onBeforeUnmount(() => {
  let add = localStorage.getItem("xhladd");
  if (!add) {
  } else {
    web3Modal.clearCachedProvider();
  }
});
//logintwitter
let twitterlog = () => {
  ongb();
  loginan.value = 1;
  hello.init(
    {
      twitter: "6F6Kw3ed2iRveFmojHckvB6ad",
    },
    {
      redirect_uri: "https://x-share-bot-delta.vercel.app/",
    }
  );
  hello("twitter")
    .login()
    .then(
      function (res) {
        console.log(res, "good");
        Twittername.value = res.authResponse.screen_name;
        xxhladdress.value = res.authResponse.screen_name;
        localStorage.setItem("Twname", Twittername.value);
      },
      function (err) {
        console.log("err", err);
      }
    );

  hello.on("auth.login", (result) => {
    hello(result.network)
      .api("/me")
      .then(
        function (p) {
          console.log(result, "result");
        },
        function (err) {
          console.log("err", err);
        }
      );
  });
};
onMounted(() => {
  //logingoogle

  setTimeout(() => {
    dhisshow.value = 1;
  }, 1000);
  bus.$on("qbbalance", (val) => {
    if (val != "" && val != "0.00") {
      loginan.value = "1";
      xxhladdress.value =
        localStorage.getItem("xhladd").substring(0, 4) +
        "..." +
        localStorage
          .getItem("xhladd")
          .substring(
            localStorage.getItem("xhladd").length - 4,
            localStorage.getItem("xhladd").length
          );
    }
  });
  if (localStorage.getItem("xhladd")) {
    xxhladdress.value =
      localStorage.getItem("xhladd").substring(0, 4) +
      "..." +
      localStorage
        .getItem("xhladd")
        .substring(
          localStorage.getItem("xhladd").length - 4,
          localStorage.getItem("xhladd").length
        );
  } else if (localStorage.getItem("Twname")) {
    xxhladdress.value = localStorage.getItem("Twname");
    Twittername.value = localStorage.getItem("Twname");
  }
  if (!xxhladdress.value) {
    loginan.value = 0;
  } else {
    loginan.value = 1;
  }
  if (localStorage.getItem("Twname")) {
    Twittername.value = localStorage.getItem("Twname");
  }
  bus.$on("Twname", (val) => {
    Twittername.value = val;
  });
});
let handleCredentialResponse = async (response) => {
  let code = response.credential;
  console.log(code);
};
let onClickHandler = (user) => {
  console.log(user, "Sign in");
};
//web3modal
let web3Modal = {};
const connect = async () => {
  const WalletConnect = window.WalletConnectProvider.default;
  const Fortmatic = window.Fortmatic;
  const providerOptions = {
    fortmatic: {
      package: Fortmatic,
      options: {
        // Mikko's TESTNET api key
        key: "pk_test_391E26A3B43A3350",
      },
    },
    walletconnect: {
      package: WalletConnect,
      options: {
        rpc: {
          56: "https://bsc-dataseed.binance.org/",
          97: "https://data-seed-prebsc-1-s1.binance.org:8545/",
        },
        network: "binance",
      },
    },
  };

  web3Modal = new Web3Modal({
    network: "mainnet", // optional
    cacheProvider: true, // optional
    providerOptions, // required
  });
  const externalProvider = await web3Modal.connect();
  return new ethers.providers.Web3Provider(externalProvider);
};
const render = async () => {
  const provider = await connect();
  const signer = provider.getSigner(0);
  xhladdress.value = await signer.getAddress();
  xxhladdress.value =
    xhladdress.value.substring(0, 4) +
    "..." +
    xhladdress.value.substring(
      xhladdress.value.length - 4,
      xhladdress.value.length
    );
  ongb();
  loginan.value = 1;
  localStorage.setItem("xhladd", xhladdress.value);
  const rawBalance = await provider.getBalance(xhladdress.value);
  xethbalance.value = ethers.utils.formatEther(rawBalance);
  localStorage.setItem("xhlbalance", xethbalance.value);
  bus.$emit("qbbalance", xethbalance.value);
};
//clone
let ongb = () => {
  showno.value = 0;
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
logTlgConnect("");
</script>

<style>
.ymainbt {
  position: relative;
}
.twxname {
  font-family: "Poppins";
  display: inline-flex;
  justify-content: center;
  align-items: center;
  column-gap: 0.5rem;
  height: 3.5rem;
  padding: 0 1.5rem;
  border-radius: 1rem;
  font-size: 16px;
  font-weight: 500;
  transition: all 0.2s;
  box-sizing: border-box;
  background: transparent;
  box-shadow: inset 0 0 0 2px #f7f7f8bf;
  color: #f7f7f8bf;
}
.twxname > svg {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
}
.ymainhy .twxname {
  box-shadow: inset 0 0 0 2px #272e35bf;
  color: #272e35;
}
.yheadapps {
  align-items: center;
  column-gap: 1rem;
  margin-right: 2rem;
}
.yheadapps > a {
  font-family: "Inter";
  font-size: 1rem;
  color: rgb(110 117 124);
}
.ymainbt .yheadapps > a:hover {
  color: rgb(238 239 242);
}
.twxname > svg {
  width: 2rem;
}
.twxnamenone {
  display: none;
}
.ymianbtbg {
  width: 100%;
  perspective: 50vmin;
  position: fixed;
  top: 40%;
  transform: scale(2);
  background-image: radial-gradient(transparent, rgba(103, 58, 183, 0.18)),
    linear-gradient(
      -90deg,
      rgba(32, 0, 88, 0.49),
      #000,
      rgba(156, 39, 176, 0.169)
    ),
    linear-gradient(
      0deg,
      rgba(255, 152, 0, 0.18),
      #000,
      rgba(139, 195, 74, 0.369)
    );
  background-color: #000;
  box-shadow: inset 0 0 150vmin 11vmin #000;
}
.ybg {
  position: absolute;
  left: 50%;
  box-shadow: -411px -476px #ccc, 777px -407px #d4d4d4, -387px -477px #fcfcfc,
    -91px -235px #d4d4d4, 491px -460px #f7f7f7, 892px -128px #f7f7f7,
    758px -277px #ededed, 596px 378px #ccc, 647px 423px #f5f5f5,
    183px 389px #c7c7c7, 524px -237px #f0f0f0, 679px -535px #e3e3e3,
    158px 399px #ededed, 157px 249px #ededed, 81px -450px #ebebeb,
    719px -360px #c2c2c2, -499px 473px #e8e8e8, -158px -349px #d4d4d4,
    870px -134px #cfcfcf, 446px 404px #c2c2c2, 440px 490px #d4d4d4,
    414px 507px #e6e6e6, -12px 246px #fcfcfc, -384px 369px #e3e3e3,
    641px -413px #fcfcfc, 822px 516px #dbdbdb, 449px 132px #c2c2c2,
    727px 146px #f7f7f7, -315px -488px #e6e6e6, 952px -70px #e3e3e3,
    -869px -29px #dbdbdb, 502px 80px #dedede, 764px 342px #e0e0e0,
    -150px -380px #dbdbdb, 654px -426px #e3e3e3, -325px -263px #c2c2c2,
    755px -447px #c7c7c7, 729px -177px #c2c2c2, -682px -391px #e6e6e6,
    554px -176px #ededed, -85px -428px #d9d9d9, 714px 55px #e8e8e8,
    359px -285px #cfcfcf, -362px -508px #dedede, 468px -265px #fcfcfc,
    74px -500px #c7c7c7, -514px 383px #dbdbdb, 730px -92px #cfcfcf,
    -112px 287px #c9c9c9, -853px 79px #d6d6d6, 828px 475px #d6d6d6,
    -681px 13px #fafafa, -176px 209px #f0f0f0, 758px 457px #fafafa,
    -383px -454px #ededed, 813px 179px #d1d1d1, 608px 98px #f5f5f5,
    -860px -65px #c4c4c4, -572px 272px #f7f7f7, 459px 533px #fcfcfc,
    624px -481px #e6e6e6, 790px 477px #dedede, 731px -403px #ededed,
    70px -534px #ccc, -23px 510px #cfcfcf, -652px -237px #f5f5f5,
    -690px 367px #d1d1d1, 810px 536px #d1d1d1, 774px 293px #c9c9c9,
    -362px 97px #c2c2c2, 563px 47px #dedede, 313px 475px #e0e0e0,
    839px -491px #e3e3e3, -217px 377px #d4d4d4, -581px 239px #c2c2c2,
    -857px 72px #ccc, -23px 340px #dedede, -837px 246px #fff,
    170px -502px #cfcfcf, 822px -443px #e0e0e0, 795px 497px #e0e0e0,
    -814px -337px #cfcfcf, 206px -339px #f2f2f2, -779px 108px #e6e6e6,
    808px 2px #d4d4d4, 665px 41px #d4d4d4, -564px 64px #ccc, -380px 74px #cfcfcf,
    -369px -60px #f7f7f7, 47px -495px #e3e3e3, -383px 368px #f7f7f7,
    419px 288px #d1d1d1, -598px -50px #c2c2c2, -833px 187px #c4c4c4,
    378px 325px #f5f5f5, -703px 375px #d6d6d6, 392px 520px #d9d9d9,
    -492px -60px #c4c4c4, 759px 288px #ebebeb, 98px -412px #c4c4c4,
    -911px -277px #c9c9c9;
  height: 0.25rem;
  width: 0.25rem;
  border-radius: 2px;
  animation: sf-fly-by 7s linear infinite;
  animation-delay: -3s;
}
@keyframes sf-fly-by {
  0% {
    transform: translateZ(-40vw);
    opacity: 0;
  }
  20% {
    opacity: 0.7;
  }
  80% {
    opacity: 0.7;
  }
  100% {
    transform: translateZ(0);
    opacity: 0;
  }
}
.yheadslau {
  display: block;
  margin-left: 0.25rem;
}
.yheadslaunone {
  display: none;
}

.yheadslau > a {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem 1.5rem;
  box-shadow: 0 0 #0000, 0 0 #0000, 0 1px 2px 0 rgb(0 0 0 / 0.05);
  background: rgb(255 110 48);
  border-radius: 1rem;
  font-family: "Poppins";
  font-size: 1rem;
  line-height: 1.5rem;
  color: rgb(247 247 248);
}
.yheadslau:hover > a {
  background: rgb(252 75 0);
}
.yddhshowy {
  display: flex !important;
}
.istwdl {
  cursor: pointer !important;
}
.yddhshow {
  width: 1.5rem;
  height: 1.5rem;
  display: none;
}

.yddhshow > svg {
  width: 1.5rem;
  height: 1.5rem;
}
.lengqh {
  width: 1.25rem;
  height: 1.25rem;
  position: relative;
}
.lengqh > svg {
  width: 100%;
  height: 100%;
}
.lengqh:hover > .lengbox {
  display: block;
}
.lengbox {
  display: none;
  position: absolute;
  top: 100%;
  left: -1.65rem;
  background: rgb(17, 11, 11);
  color: white;
  padding: 0.25rem 0;
  border: 2px solid rgb(179 187 202);
  border-radius: 0.375rem;
  margin-top: 0.5rem;
}
.ymainhy .lengbox {
  border-color: #000;
  background: transparent;
}
.lengbox > span {
  display: block;
  width: 0.5rem;
  height: 0.5rem;
  border: 0.5rem solid transparent;
  border-bottom: 0.5rem solid rgb(179 187 202);
  box-sizing: border-box;
  position: absolute;
  top: -1rem;
  left: 50%;
  transform: translate(-50%);
}
.ymainhy .lengbox > span {
  border-bottom-color: black;
}
.lengbox > div {
  padding: 0 0.5rem;
  cursor: pointer;
  text-align: center;
}
.lengbox > div:hover {
  background: #b3bbca;
}
.ymainhy .lengbox > div {
  color: rgb(105 111 122);
}
.ymainhy .lengbox > div:hover {
  background: white;
}
.lengqh > img {
  width: 100%;
  height: 100%;
}
.ymainhy .lengqh > img {
  content: url("./assets/globalblack.svg");
}
.ymainhy .yddhshow > svg {
  fill: rgb(17, 11, 11);
}

.yddhshow > svg {
  fill: #fff;
  cursor: pointer;
}

.ymainhy .ydddh {
  background: #fff;
}

.ydddh {
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0%;
  justify-content: center;
  align-items: center;
  background: black;
  z-index: 1000;
  display: none;
}

.ydddhl > a {
  display: block;
  font-size: 2rem;
  margin: 2rem 0;
  text-align: center;
  line-height: 2rem;
  color: white;
  font-family: "Poppins";
}

.ymainhy .ydddhl > a {
  color: #000;
}

.dhhidd {
  display: none;
}

.dhshow {
  position: fixed;
  top: 0;
  left: 0;
  background: rgb(17, 11, 11);
  width: 100vw;
  height: 100vh;
  z-index: 10000;
  justify-content: center;
  align-items: center;
}

.anidh {
  align-items: center;
}
.anidh > img {
  width: 8.5rem;
  height: auto;
}
.anidh > span {
  color: white;
  font-family: "Poppins";
  font-size: 4rem;
  line-height: 3.5rem;
}
.ydisnone {
  display: none;
}

.ymain {
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(0, 0, 0, 0.25);
  width: 100vw;
  height: 100vh;
  position: fixed;
  z-index: 500;
  top: 0;
}

.ybuts {
  width: 25.6rem;
  border-radius: 1rem;
  background: rgba(0, 0, 0, 0.75);
  padding: 2rem;
  box-sizing: border-box;
  position: relative;
}

.ybutbg {
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  height: 0.75rem;
  background: linear-gradient(
    to bottom,
    rgb(23, 29, 35) 0%,
    rgba(84, 184, 245, 0.5) 100%
  );
  border-top-right-radius: 1rem;
  border-top-left-radius: 1rem;
}

.ybuts > button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 60%;
  padding: 0.5rem 0.75rem;
  box-sizing: border-box;
  border: 1px solid #dadce0;
  font-weight: 700;
  color: rgb(15 20 25);
  margin: 1rem auto;
  background: #fff;
  border-radius: 1.5rem;
  column-gap: 0.5rem;
  cursor: pointer;
  font-size: 1rem;
}

.ybuts > h2 {
  font-size: 2rem;
  line-height: 2rem;
  color: #fff;
  text-align: center;
}

.ybuts > button:hover {
  background: rgb(230, 230, 230);
}

.ybuts > button > svg {
  width: 1.5rem;
  height: 1.5rem;
}

.ybuts > button > img {
  width: 1.5rem;
  height: 1.5rem;
}

.dkeor {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 1.375rem;
  margin: 1rem auto 0.5rem;
  padding: 0.5rem 0.75rem;
  box-sizing: border-box;
}

.dkehs {
  width: 39%;
  height: 1px;
  background: rgba(255, 255, 255, 0.35);
  font-weight: 700;
}

.dkeor > span {
  font-style: normal;
  font-weight: 400;
  font-size: 1rem;
  line-height: 1.125rem;
  color: #f8f8f8;
  padding: 0 1rem;
}

.ythricon {
  display: flex;
  justify-content: center;
  align-items: center;
  column-gap: 1.5rem;
  padding: 0 0 1rem;
}

.ytwitter {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
  background: #fff;
  cursor: pointer;
  position: relative;
  border: 1px solid #fff;
  transition: border-color 0.218s;
  box-sizing: border-box;
  overflow: hidden;
}

.ytwitter:hover {
  border-color: #d2e3fc;
}

.ytwitter > svg {
  width: 85%;
  height: 100%;
  position: absolute;
  left: 0.2rem;
  top: 0;
  transform: scale(0.7);
}

.dkeendtxt {
  width: 100%;
  padding: 0 1.25rem;
  font-style: normal;
  font-weight: 400;
  font-size: 0.75rem;
  line-height: 1rem;
  text-align: center;
  color: #9d9d9d;
  box-sizing: border-box;
}

.gb {
  width: 2rem;
  cursor: pointer;
  position: absolute;
  left: 50%;
  bottom: -3rem;
  transform: translate(-50%);
}

.ycont {
  width: 100%;
  height: 100vh;
  position: relative;
  overflow: hidden;
}

.ycont > video {
  width: 110%;
  position: absolute;
  z-index: 1;
  left: 0;
  transform: translate(-5%);
}

.ycontbut {
  width: 100%;
  position: absolute;
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 20%;
  column-gap: 1.25rem;
}

.ycontbut > a {
  width: 2rem;
}

.ycontbut > a > img {
  width: 100%;
}

@media (max-width: 1250px) {
  .ycont > video {
    width: 384%;
    transform: translate(-37%);
  }

  .cornered-button {
    font-size: 1.25rem;
  }

  .dhshow > img {
    width: 60%;
  }
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.ymainbt .hyshow {
  display: none;
}

.ymainhy .btshow {
  display: none;
}

.fixtop {
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
}

.yhead {
  width: 100%;
  height: 5.5rem;
  padding: 1rem;
  box-sizing: border-box;
  background: rgb(30, 37, 43);
}

.ymainhy .yhead {
  background: white;
}

.yheadbox {
  width: 63.5%;
  height: 100%;
  margin: 0 auto;
  align-items: center;
}

.yheads {
  align-items: center;
  column-gap: 0.75rem;
}
.yheady {
  align-items: center;
}
.yheady > a:nth-child(1) {
  width: 7.5rem;
  height: 1.9375rem;
}

.yheady > a > svg {
  width: 100%;
  height: 100%;
}

.yheady > a > img {
  width: 100%;
  height: 100%;
}

.yheady {
  align-items: center;
  column-gap: 1.5rem;
}

.yheady > a {
  font-family: "Inter";
  font-size: 1rem;
  color: rgb(110 117 124);
}
/* .yheade > a:nth-child(7) {
  cursor: not-allowed !important;
} */
.ymainbt .yheady > a {
  color: rgb(110 117 124);
}

.ymainbt .yheady > a:hover {
  color: rgb(238 239 242);
}

.ymainhy .yheady > a {
  color: rgb(17 11 11);
}

.ymainhy .yheady > a:hover {
  color: rgb(56 59 64);
}
.ymainhy .yheady .hyshowimg {
  content: url("./assets/newlogo.png");
}
.qihuan {
  line-height: 1;
  cursor: pointer;
}

.ymainbt .qihuan {
  color: rgb(179 187 202);
}

.ymainhy .qihuan {
  color: rgb(56 59 64);
}

.yheade {
  align-items: center;
  column-gap: 1rem;
}

.yheade > a {
  font-family: "Vectrex";
  font-size: 1rem;
  color: #fff;
}
/* .yheade > a:nth-child(7) {
  cursor: not-allowed !important;
} */
.ymainbt .yheade > a {
  color: #fff;
}

.ymainbt .yheade > a:hover {
  color: rgb(179 187 202);
}

.ymainhy .yheade > a {
  color: rgb(17 11 11);
}

.ymainhy .yheade > a:hover {
  color: rgb(56 59 64);
}

.yheaddisc {
  position: relative;
}

.yheaddisc > button {
  cursor: not-allowed !important;
}

.yheaddisc:hover .yheaddc {
  display: block !important;
}

.yheaddc {
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  z-index: 100;
  display: none;
}

.yheaddc span {
  display: block;
  width: 0.5rem;
  height: 0.5rem;
  border: 0.5rem solid transparent;
  border-bottom: 0.5rem solid rgb(179 187 202);
  box-sizing: border-box;
  position: absolute;
  top: -0.5rem;
  left: 50%;
  transform: translate(-50%);
}

.yheaddc button {
  width: 100%;
  margin-top: 0.5rem;
}

.yheads button {
  font-family: "Vectrex";
  width: 11.5rem;
  border: 2px solid;
  border-radius: 0.375rem;
  height: 3rem;
  font-weight: 400;
  font-size: 1rem;
  background: transparent;
  cursor: pointer;
}

.ymainbt .yheads button {
  border-color: rgb(179 187 202);
  color: rgb(255 255 255);
}

.ymainbt .yheads button:hover {
  border-color: rgb(255 255 255);
}

.ymainhy .yheads button {
  border-color: rgb(105 111 122);
}

.ymainhy .yheads button:hover {
  border-color: rgb(17 11 11);
}

.ymainhy .yheaddc span {
  border-bottom-color: rgb(105 111 122);
}

.ymainhy .yheaddc button {
  border-color: rgb(235, 235, 235);
  color: white;
}

.ymainhy .yheaddc button:hover {
  border-color: white;
}

.yht {
  width: 100%;
  background: rgb(23 29 35);
  font-size: 0.75rem;
  line-height: 1rem;
  padding: 0.5rem 0;
  justify-content: center;
  align-items: center;
  column-gap: 2rem;
}

.ymainhy .yht {
  background: rgb(17 11 11);
}

.yht > a {
  font-family: "Poppins";
  color: rgb(84 184 245);
  align-items: center;
  column-gap: 0.75rem;
  line-height: 1rem;
  opacity: 0.75;
  transition: all 0.3s;
}

.yht > a:hover {
  opacity: 1;
}

.ymainhy .yht > a {
  color: rgb(255 255 255);
}

.yht > a > .jiantl {
  color: rgb(111 198 81);
}

.yht > a > .jiantr {
  color: rgb(232 90 67);
}

.yfoot {
  padding-top: 3rem;
  width: 100%;
  background: rgb(30, 37, 43);
  color: rgb(255, 255, 255);
}

.ymainhy .yfoot {
  background: white;
  background: url("./assets/homebgw.png");
  color: rgb(0, 0, 0) !important;
}

.yfootboxer {
  width: 63.5%;
  margin: 0 auto;
  /* border-top: 1px solid rgb(56 59 64); */
  padding: 4rem 0 6rem;
  column-gap: 2rem;
}

.yfootbeleft {
  max-width: 24rem;
}

.yfootbeleft > svg {
  width: 12rem;
  height: 2.3125rem;
  margin-bottom: 1rem;
}

.yfootbeleft > img {
  width: 12rem;
  height: 2.3125rem;
  margin-bottom: 1.5rem;
}

.ymainhy .yfootbeleft > img {
  content: url("./assets/black.png");
}

.yfootbeleft p {
  font-family: "Inter";
  color: #6e757c;
  text-align: left;
  margin-bottom: 1rem;
  font-weight: 500;
  font-size: 1rem;
  line-height: 1.5rem;
}

.ymainhy .yfootbeleft p {
  color: rgb(105 111 122);
}

.yfootblas {
  align-items: center;
  column-gap: 2rem;
}

.yfootblas > a {
  width: 1.8rem;
  height: 1.5rem;
}

.yfootblas > a > svg {
  width: 100%;
  height: 1.5rem;
  color: rgb(255 255 255);
  margin: 0;
}

.ymainhy .yfootblas > a > svg {
  color: rgb(17 11 11);
}

.yfootberight {
  justify-content: flex-end;
  flex: 1 1 0%;
  column-gap: 4rem;
}

.yfootberiy {
  flex-direction: column;
  gap: 1rem;
}

.yfootberiy a {
  font-family: "Inter";
  font-size: 1rem;
  line-height: 1.5rem;
  color: rgb(110 117 124);
  font-weight: 500;
  transition: all 0.15s;
}

.yfootberiy a:hover {
  color: #fff;
}

.ymainhy .yfootberiy a {
  color: rgb(105 111 122);
}

.ymainhy .yfootberiy a:hover {
  color: rgb(56 59 64);
}

.yfootboxsan {
  width: 100%;
  background: rgb(0, 0, 0);
}

.ymainhy .yfootboxsan {
  background: rgb(179, 187, 202);
}

.yfootbscon {
  width: 63.5%;
  margin: 0 auto;
  padding: 1rem 0;
  box-sizing: border-box;
  gap: 1rem;
  align-items: center;
  font-size: 1rem;
  line-height: 1.5rem;
  color: #696f7a;
  font-family: "Inter";
}

.ymainhy .yfootbscon {
  color: rgb(17 11 11);
}

.yfootbscon > span {
  margin-right: 1rem;
}

.yfootbscon > a {
  color: #696f7a;
  transition: all 0.15s;
}

.ymainhy .yfootbscon > a {
  color: rgb(17 11 11);
}

.yfootbscon > a:hover {
  color: #b3bbca;
}

.ymainhy .yfootbscon > a:hover {
  color: rgb(56 59 64);
}

@media (max-width: 1225px) {
  .yheadapps {
    display: none;
  }

  .anidh > img {
    width: 4.5rem;
  }
  .anidh > span {
    font-size: 2rem;
  }
  .yheadslau > a {
    padding: 0.5rem 0.75rem;
    font-size: 0.75rem;
    border-radius: 0.65rem;
  }
  .yfootberiy {
    margin-bottom: 1rem;
  }
  .twxname {
    display: none;
  }
  .yddhshow {
    display: block;
  }
  .yheads button {
    width: 7.5rem;
    padding: 0 0.2rem;
    box-sizing: border-box;
  }
  .yheady > a:nth-child(5) {
    display: none;
  }
  .yheadbox {
    width: 100%;
    display: flex;
  }

  .app_two {
    margin-left: 0.5rem !important;
  }

  .flex {
    flex-wrap: nowrap;
  }

  .yheade {
    display: none;
  }
  .yheady > a:nth-child(2) {
    display: none;
  }
  .yheady > a:nth-child(3) {
    display: none;
  }
  .yheady > a:nth-child(4) {
    display: none;
  }
  .yheady > a:nth-child(6) {
    display: none;
  }
  .yheady > a:nth-child(7) {
    display: none;
  }
  .yhead {
    padding: 1rem 0.5rem;
    height: 3.5rem;
  }

  .ymainbt .yheads button {
    font-size: 10px;
    height: 2rem;
    width: 7rem;
    padding: 0 0.25rem;
  }

  .yht {
    overflow: hidden;
    column-gap: 0.25rem;
  }

  .yht > a {
    font-size: 7px;
    column-gap: 0.25rem;
  }

  .yoneboxy {
    display: none;
  }

  .yhomey {
    width: 100% !important;
    padding: 2.5rem 1rem !important;
    box-sizing: border-box;
  }

  .yone {
    display: none;
  }

  .yheads {
    height: 2rem;
    column-gap: 0.15rem;
  }

  .yhomeyright {
    width: 95% !important;
    top: 14.5rem !important;
    right: 2.5% !important;
  }

  .ybiao_two > h2 {
    font-size: 1.875rem !important;
    line-height: 2.25rem !important;
  }

  .yhomeyright > p {
    font-size: 1.25rem !important;
  }

  .yhomeyleft > svg:nth-child(1) {
    width: 100%;
  }

  .yhomeyleft > svg:nth-child(2) {
    width: 100%;
  }

  .yhomeytxtc {
    font-size: 1rem !important;
    line-height: 1.5rem !important;
  }

  .ymainhy .yheads button {
    font-size: 12px;
    height: 2rem;
  }

  .yhomeyright a {
    justify-content: center;
  }

  .yhomeyright a svg {
    width: 60% !important;
    height: 4.5rem !important;
  }

  #xShareBot .ytwoleft {
    width: 100%;
  }

  #xShareBot .ytworight {
    width: 100%;
    text-align: center;
    margin-top: 3rem;
  }

  #MevBot .ytwoleft {
    width: 100%;
  }

  #MevBot .ytworight {
    width: 100%;
    text-align: center;
    margin-top: 3rem;
  }

  .yfootbox {
    width: 100%;
    padding: 4rem 2rem;
  }

  .yfootbox > h2 {
    font-size: 26px;
  }

  .yfootbox > a {
    height: 3rem;
    line-height: 3rem;
  }

  .yfootboxer {
    width: 100%;
    display: flex;
    flex-direction: column;
  }

  .yfootbeleft p {
    text-align: center;
  }

  .yfootbeleft {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .yfootberight {
    margin-top: 3rem;
    display: flex !important;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .yfootbscon {
    justify-content: center;
    width: 100%;
  }

  .ybuts {
    width: 90%;
  }

  .ybuts > button {
    width: 66%;
  }
}

@media screen and (min-width: 1801px) {
  .yfootbox {
    width: 58%;
  }

  .yfootboxer {
    width: 58%;
  }

  .yfootbscon {
    width: 58%;
  }

  .yheadbox {
    width: 63.5%;
  }

  .yhomey {
    width: 60% !important;
  }
}

@media screen and (max-width: 1650px) {
  .yheade {
    column-gap: 1rem;
  }
  .yheadbox {
    width: 80%;
  }
}

@media screen and (max-width: 1301px) {
  .yheadbox {
    width: 100%;
  }
}
</style>
