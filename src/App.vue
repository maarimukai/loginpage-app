<template>
  <main>
    <div id="firstSection">
      <img class="logo" alt="Grab Logo" src="./assets/logo-grab.svg">
      <div class="loginSection">
        <span class="p-input-icon-left">
            <i class="pi pi-at"/>
            <InputText class="inputs" type="text" v-model="value" placeholder="" />
        </span>
        <span class="p-input-icon-left">
            <i class="pi pi-lock"/>
            <InputText class="inputs" type="password" v-model="password" placeholder="" />
        </span>
        <Button label="Submit" class="btn"/>
        <div class="aptag">
            <p>problems to get in?</p>
            <a href=""><strong>click here</strong></a>
        </div>
      </div>
    </div>
    <div>
      <img class="imageSection" src="./assets/undraw_interview_rmcf.svg" alt="Interview">
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      value: "",
      password: ""
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&family=Roboto:wght@400;700&display=swap');
#app {
  font-family: Roboto, sans-serif;
}

#firstSection {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #4E5BEE;
  width: 550px;
  height: 640px;
  position: absolute;
}

.loginSection {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.logo {
  width: 160px;
  height: 63.2px;
  margin-top: 80px;
  margin-bottom: 80px
}

.p-input-icon-left {
  margin: 5px;
}

.inputs {
  background-color: #4E5BEE !important;
  border: 2px solid #F8F8F8 !important;
  border-radius: 15px !important;
  width: 250px;
}

i {
  color: #F8F8F8 !important;
  padding-left: 5px;
}

.btn {
  margin-top: 15px !important;
  margin-bottom: 50px !important;
  width: 250px;
  background-color: #F8F8F8 !important;
  border-radius: 15px !important;
  color: #605f6f !important;
}

.aptag {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 70px;
  font-size: 12px;
}

p {
  color: #F8F8F8;
  margin: 5px;
}

a {
  color: #F8F8F8;
  text-decoration: none;
}

.imageSection {
  /* 1084.140x758.562 */
  width: 924.14px;
  height: 598.562px;
  margin-left: 350px;
  margin-top: 30px;
}

</style>
