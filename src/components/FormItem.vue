<template>
  <form class="form">
    <div class="form__title">NFT Access</div>
    <div class="form__desc">
      Please fill your detail to access your account.
    </div>
    <label class="forms">
      <span class="forms__title">Emeil</span>
      <div class="forms__input-wrapper">
        <Input
          class="forms__input"
          title="Emeil"
          type="emeil"
          name="emeil"
          placeholder="Your emeil"
          v-model="inputValue"
        />
        
        <div class="paswword">
          <span class="forms__title">Password</span>
          <Input
            class="forms__input"
            title="Password"
            :type="showPassword ? 'text' : 'password'"
            name="password"
            placeholder="Your password"
            v-model="passwordValue"
          />
        </div>

        <div className="forms__input-svg">
          <span  class="clear" @click="clearInput"><img src="./Icons/ClearIcon.svg" alt=""></span>
         <!-- <span class="yaedefault"  @click="togglePasswordVisibility"><img src="./Icons/YaedefaultIcon.svg" alt=""></span>  --> 
          <span class="yaedefault" :class="showPassword ? 'fa-eye-slash' : 'fa-eye'" @click="togglePasswordVisibility"><img src="./Icons/YaeIcon.svg" alt=""></span>
        </div>
      </div>
    </label>
    <div class="custom-checkbox" @click="toggleChecked">
      <div class="checkbox-icon" :class="{ checked: isChecked }">
        <svg v-if="isChecked" xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 12 12">
          <path fill="#ffffff" d="M11.296.305a.585.585 0 01.008.82l-7.47 7.853a.6.6 0 01-.863 0L.695 5.56a.585.585 0 01.817-.83l2.98 2.924L10.48.305a.585.585 0 01.816 0z"/>
        </svg>
      </div>
      <label class="checkbox-label">Remember me</label>
         <a href="/">Forgot Password?</a>
    </div>
    <div class="form__btn">
      <Button class="btn__primary">Sign in</Button>
      <Button class="btn__secondary">
        <img
          src="./Icons/GoogleIcon.svg
              "
          alt="Google"
        />
        Sign in with Google
      </Button>
    </div>
    <div class="row__center">
      Don’t have an account?
      <a href="/">Sign up</a>
    </div>
  </form>
</template>

<script>
export default {
  props: {
    label: String,
    value: Boolean
  },
data() {
  return {
    inputValue: '',
    password: '',
    showPassword: false,
    isChecked: this.value
  };
},
methods: {
  clearInput() {
    this.inputValue = ''; 
  },
  togglePasswordVisibility() {
      this.showPassword = !this.showPassword;
  },
  toggleChecked() {
      this.isChecked = !this.isChecked;
      this.$emit('input', this.isChecked);
    }
}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form {
  max-width: 360px;
  margin: auto;
}
.form__title {
  color: #344054;
  font-family: Inter;
  font-size: 40px;
  font-weight: 700;
  letter-spacing: 0.4px;
  text-transform: capitalize;
  margin-bottom: 8px;
}
.form__desc {
  color: #667085;
  font-family: Inter;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
  margin-bottom: 56px;
}

.forms {
  display: block;
}
.forms :not(:last-child) {
  margin-bottom: 20px;
}
.forms__title {
  color: #344054;
  font-family: Inter;
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
}

.forms__input-wrapper {
  display: grid;
  position: relative;
}
.forms__input-svg {
  position: absolute;
  top: 21px;
  right: 14px;
  cursor: pointer;
  background: transparent;
}
.yaedefault {
  position: absolute;
  top: 92px;
  right: 0;
}
.forms__input {
  margin-top: 8px;
  height: 44px;
  width: 100%;
  display: block;
  padding: 10px 14px;
  color: #667085;
  font-family: Inter;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
  border-radius: 8px;
  border: 1px solid #d0d5dd;
  background: transparent;
}

.row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 20px;
}
input {
  display: none;
}
.row__center {
  display: flex;
  justify-content: center;
  gap: 4px;
}

a {
  color: #5429ff;
  font-family: Inter;
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
}
.custom-checkbox {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.checkbox-icon {
  width: 16px;
  height: 16px;
  border: 1px solid #d0d5dd;
  border-radius: 4px;
  margin-right: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.2s;
}

.checkbox-icon.checked {
  background-color: #5429FF;
  border-color: #5429FF;
}

.checkbox-icon svg {
  transform: scale(0);
  transition: transform 0.2s;
}

.custom-checkbox:hover .checkbox-icon svg {
  transform: scale(1);
}

.checkbox-label {
  color: #344054;
  font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: 20px;
  padding-right: 113px;
}
.form__btn {
  display: grid;
  gap: 16px;
  margin-top: 32px;
  margin-bottom: 20px;
}

.btn__primary {
  width: 100%;
  padding: 12px;
  border: 0;
  outline: 0;
  border-radius: 8px;
  background: #5429ff;
  color: #fff;
  font-family: Inter;
  font-size: 16px;
  font-weight: 500;
  line-height: 20px;
  cursor: pointer;
}

.btn__secondary {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  width: 100%;
  padding: 12px;
  border-radius: 8px;
  border: 1px solid #d0d5dd;
  color: #344054;
  font-family: Inter;
  font-size: 16px;
  font-weight: 500;
  line-height: 20px;
  background: transparent;
  cursor: pointer;
}
</style>
