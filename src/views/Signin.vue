<template>
  <div class="container">
    <form action="/" id="form">
      <div class="title">
        <h1>Welcome</h1>
        <p>Let's make the job done together.</p>
      </div>
      <Input
        :form_control="isEmailErr ? 'g-form-control g-error' : 'g-form-control'"
        label_text="Email"
        input_placeHolder="Enter your email address"
        :msg_text="email_msg_err"
        input_type="text"
        for_name="email"
        ref="emailRef"
        v-model.trim="emailValue"
      />
      <Input
        :form_control="isPasswordErr ? 'g-form-control g-error' : 'g-form-control'"
        label_text="Password"
        input_placeHolder="Password"
        :msg_text="password_msg_err"
        input_type="password"
        for_name="password"
        ref="passwordRef"
        v-model.trim="passwordValue"
      />
      <div class="remember-me">
        <Checkbox checkbox_label="Remember Me" for_name="checkbox" />
      </div>
      <div class="submit">
        <Button
          btn_text="Login"
          class="g-btn g-btn-primary custom-btn"
          @check="clicked"
        />
        <div class="divider">Or</div>
        <Button btn_text="Sign Up" class="g-btn g-btn-tertiary custom-btn" />
      </div>
    </form>

    <div class="maker">
      <p>Made by</p>
      <img src="../assets/heart.png" alt="heart" />
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import Checkbox from "../components/Checkbox.vue";
import Input from "../components/Input.vue";

export default {
  name: "Sign-in",
  data() {
    return {
      email: "ah.mohsen001@gmail.com",
      password: "alijan@123",
      emailValue: "",
      passwordValue: "",
      email_msg_err: "Email is Required!",
      password_msg_err: "Password is Required!",
      isEmailErr: false,
      isPasswordErr: false,
      page: false
    };
  },
  components: {
    Button,
    Checkbox,
    Input,
  },
  methods: {
    clicked() {
      // e.preventDefault();
      // this.$refs.emailRef.checkEmail();
      const emailValidation = () => {
        if (this.emailValue == "") {
          this.isEmailErr = true;
          this.email_msg_err = "Email is Required!";
        } else if (this.emailValue !== this.email) {
          this.isEmailErr = true;
          this.email_msg_err = "Email is incorrect!";
        } else {
          this.isEmailErr = false;
        }
      };  

      const passwordValidation = () => {
        if (this.passwordValue == "") {
          this.isPasswordErr = true;
          this.password_msg_err = "Password is Required!";
        } else if (this.passwordValue !== this.password) {
          this.isPasswordErr = true;
          this.password_msg_err = "Password is incorrect!";
        } else {
          this.isPasswordErr = false;
        }
      }

      emailValidation();
      passwordValidation();

      // if (this.page) {
      //   this.$router.push('/signup')
      // }
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

#form {
  background-color: white;
  padding: 30px 50px;
  border-radius: 20px;
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

.submit {
  text-align: center;
  width: 100%;
}

.submit .divider {
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

.custom-btn {
  width: 100%;
  display: block;
  margin-bottom: 10px;
}

.remember-me {
  margin-bottom: 20px;
  /* display: flex;
  align-items: center;
  justify-content: start; */
}

.maker {
  margin-top: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.maker p {
  font-size: 12px;
  display: inline-block;
  opacity: 0.5;
}

.maker img {
  width: 14px;
  margin-left: 5px;
}
</style>
