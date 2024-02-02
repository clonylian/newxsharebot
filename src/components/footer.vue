<template>
  <div class="ynewfoot">
    <div class="ynfootbox flex jus">
      <span>@2023 NAVl. All rights reserved.</span>
      <p class="ynfootend flex">
        <router-link to="/terms" target="_blank">Terms of Service</router-link>
        <router-link to="/eigenlayer" target="_blank"
          >Privacy Policy</router-link
        >
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
  padding-top: 3.75rem;
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
.ynfootend {
  column-gap: 1rem;
}
.ymainhy .ynfootbox > span {
  color: black;
}

.ymainhy .ynfootend > a {
  color: black;
}

.ynfootend > a {
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
  .ynfootend {
    width: 100%;
    justify-content: center;
  }
}
</style>
