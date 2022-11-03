<template>
  <div class="container">
    <div class="form-holder">
      <form action="/" id="form">
        <div class="title">
          <h1>Create Account</h1>
          <p>Fill up your details below.</p>
        </div>

        <div class="name-field">
          <Input
            :form_control="
              isErr[0] ? 'g-form-control g-error' : 'g-form-control'
            "
            label_text="Firstname"
            input_placeHolder="Mohammad Mohsen"
            :msg_text="msg_err[0]"
            input_type="text"
            for_name="firstname"
            ref="passwordRef"
            v-model.trim="firstnameValue"
          />
          <Input
            :form_control="
              isErr[1] ? 'g-form-control g-error' : 'g-form-control'
            "
            label_text="Lastname"
            input_placeHolder="Ahmadi"
            :msg_text="msg_err[1]"
            input_type="text"
            for_name="lastname"
            ref="passwordRef"
            v-model.trim="lastnameValue"
          />
        </div>

        <Input
          :form_control="isErr[2] ? 'g-form-control g-error' : 'g-form-control'"
          label_text="Email"
          input_placeHolder="yourname@example.com"
          :msg_text="msg_err[2]"
          input_type="text"
          for_name="email"
          ref="passwordRef"
          v-model.trim="emailValue"
        />
        <div class="password-field">
          <Input
            :form_control="
              isErr[3] ? 'g-form-control g-error' : 'g-form-control'
            "
            label_text="Password"
            input_placeHolder="Password"
            :msg_text="msg_err[3]"
            input_type="password"
            for_name="password"
            ref="passwordRef"
            v-model.trim="passwordValue"
          />
          <Input
            :form_control="
              isErr[4] ? 'g-form-control g-error' : 'g-form-control'
            "
            label_text="Confirm Password"
            input_placeHolder="Password"
            :msg_text="msg_err[4]"
            input_type="password"
            for_name="repassword"
            ref="passwordRef"
            v-model.trim="repasswordValue"
          />
        </div>

        <div class="policy-agreement">
          <Checkbox
            checkbox_label="I agree to Terms, Privacy Policy and Fees"
            for_name="checkbox"
          />
        </div>

        <div class="submit">
          <Button
            btn_text="Login"
            class="g-btn g-btn-primary custom-btn"
            @check="signUp"
          />
          <div class="divider">Or</div>
          <Button btn_text="Sign Up" class="g-btn g-btn-tertiary custom-btn" />
        </div>
      </form>

      <div class="image">
        <img src="../assets/signup--img.jpg" alt="image" />
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import Checkbox from "../components/Checkbox.vue";
import Input from "../components/Input.vue";

export default {
  name: "Sign-up",
  data() {
    return {
      firstnameValue: "",
      lastnameValue: "",
      emailValue: "",
      passwordValue: "",
      repasswordValue: "",
      msg_err: [],
      isErr: [],
    };
  },
  components: {
    Button,
    Checkbox,
    Input,
  },
  methods: {
    signUp() {
      const ele = document.querySelectorAll("#form input:not(#checkbox)");
      const eleArr = [...ele];
      eleArr.forEach((inputValue) => {
        if (inputValue.value === "") {
          this.isErr.push(true);
          this.msg_err.push(
            `${inputValue.name
              .slice(0, 1)
              .toUpperCase()}${inputValue.name.substring(1)} is required!`
          );
        } else {
          this.isErr.push(false);
          const emailValidation = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            if (inputValue.name == 'email' && inputValue.value.match(emailValidation)) {
              console.log('worked!');
          }
        }

        
      });
    },
  },
};
</script>

<style scoped>
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url(../assets/login-bg.jpg) no-repeat;
  background-position: cover;
  flex-direction: column;
}

.form-holder {
  background-color: white;
  padding: 50px;
  border-radius: 20px;
  display: flex;
}

#form .title {
  margin-bottom: 43px;
}

#form .title h1 {
  color: var(--primary-color);
}

#form .title p {
  color: var(--primary-black);
}

::v-deep(#firstname),
::v-deep(#lastname),
::v-deep(#password),
::v-deep(#repassword) {
  width: 208px !important;
}

.g-form-control {
  margin-right: 16px;
}

.name-field {
  display: flex;
  /* flex-direction: row; */
}

.password-field {
  display: flex;
  /* flex-direction: row; */
}

::v-deep(#email) {
  width: 100%;
  margin-right: 16px;
}

/* buttons */

.submit {
  text-align: center;
  width: 100%;
}

.divider {
  font-size: 14px;
  font-weight: 700;
  color: var(--primary-black);
  opacity: 0.5;
  position: relative;
  background-color: white;
  width: 50px;
  display: inline;
  padding: 0 20px;
}

.divider::after {
  content: "";
  width: 283px;
  height: 1px;
  background-color: black;
  /* opacity: 0.3; */
  position: absolute;
  top: 50%;
  left: 0;
  transform: translate(-40%);
  z-index: -5;
  opacity: 0.3;
}

.submit .custom-btn {
  width: 100%;
  display: block;
  margin-bottom: 10px;
}

/* image  */

.image img {
  width: 512px;
  border-radius: 20px;
  margin-left: 63px;
}

.policy-agreement {
  margin-bottom: 59px;
}
</style>
