<template>
  <div class="ynewfoot">
    <div class="ynfootbox flex jus">
      <span>@2023 NAVl. All rights reserved.</span>
      <p>
        <span>Audited by </span>
        <a href="">otterSec, Movebit</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.ynewfoot {
  width: 100%;
  background: rgb(30, 37, 43);
  padding-top: 8.75rem;
}
.ymainhy .ynewfoot {
  background: white;
}
.ynfootbox {
  width: 63.5%;
  align-items: center;
  margin: 0 auto;
  border-top: 1px solid rgb(179 187 202);
  padding: 1rem 0;
}
.ynfootbox > span {
  font-family: "Inter";
  color: #6a7986;
}
.ymainhy .ynfootbox > span {
  color: black;
}
.ymainhy .ynfootbox > p {
  color: black;
}
.ymainhy .ynfootbox > p > a {
  color: black;
}
.ynfootbox > p {
  font-family: "Inter";
  color: rgb(235, 235, 235);
}
.ynfootbox > p > a {
  font-family: "Poppins";
  color: white;
}
@media (max-width: 1250px) {
  .ynfootbox {
    width: 95%;
    display: block;
    text-align: center;
  }
  .ynewfoot {
    padding-top: 2rem;
  }
}
</style>
