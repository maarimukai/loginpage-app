<template>
    <main>
        <form id="firstSection" @submit.prevent="handleSubmit(!v$.$invalid)" >
            <img class="logo" alt="Grab Logo" src="./assets/logo-grab.svg">
            <div class="p-float-label p-input-icon-left">
                <i class="pi pi-at"></i>
                <InputText class="inputs" v-model="v$.email.$model" :class="{'p-invalid':v$.email.$invalid && submitted}" aria-describedby="email-error"/>
            </div>
            <span v-if="v$.email.$error && submitted">
                <span id="email-error" v-for="(error, index) of v$.email.$errors" :key="index">
                    <small class="p-error">{{error.$message}}</small>
                </span>
            </span>
            <small v-else-if="(v$.email.$invalid && submitted) || v$.email.$pending.$response" class="p-error">{{v$.email.required.$message.replace('Value', 'Email')}}</small>
            <span class="p-input-icon-left">
                <i class="pi pi-lock"/>
                <InputText class="inputs" type="password" v-model="password" placeholder="" />
            </span>
            <Button type="submit" label="Submit" class="btn"/>
            <p>problems to get in?</p>
            <a href=""><strong>click here</strong></a>
        </form>
        <img class="imageSection" src="./assets/undraw_interview_rmcf.svg" alt="Interview">
    </main>
</template>

<script>
import { email, required } from "@vuelidate/validators";
import { useVuelidate } from "@vuelidate/core";

export default {
    setup: () => ({ v$: useVuelidate() }),
    data() {
        return {
            email: '',
            password: '',
            accept: null,
            submitted: false,
            showMessage: false,
        }
    },
    validations() {
        return {
            email: {
                required,
                email
            },
            password: {
                required
            },
        }
    },
    methods: {
        handleSubmit(isFormValid) {
            this.submitted = true;
            if (!isFormValid) {
                return;
            }
            this.toggleDialog();
        },
        toggleDialog() {
            this.showMessage = !this.showMessage;
        
            if(!this.showMessage) {
                this.resetForm();
            }
        },
        resetForm() {
            this.email = '';
            this.password = '';
            this.submitted = false;
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&family=Roboto:wght@400;700&display=swap');

body {
  margin: 0;
}

#firstSection {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  background-color: #4E5BEE;
  width: 38vw;
  height: 100%;
}

.logo {
  width: 160px;
  height: 63.2px;
  margin-top: 80px;
  margin-bottom: 80px;
}

.p-input-icon-left {
  margin: 5px;
}

.inputs {
  background-color: #4E5BEE !important;
  border: 2px solid #F8F8F8;
  border-radius: 20px !important;
  width: 250px;
  color: #F8F8F8 !important;
}

small {
  color: #F8F8F8 !important;
  margin-left: 15px;
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

p {
  color: #F8F8F8;
  margin-top: 5rem;
  margin-bottom: 0;
  font-size: 0.9rem;
}

a {
  color: #F8F8F8;
  text-decoration: none;
  font-size: 0.75rem;
}

.imageSection {
  height: 99vh;
  margin-left: 25vw;
  padding-top: 2vh;
}


</style>