<template>
  <div class="form-page">
    <div class="background">
      <div class="container" dir="rtl">
        <div class="form-wrapper">
          <div class="form-container">
            <InputComp v-model:value="firstName" label="نام" placeholder="نام را وارد کنید" type="text" />
            <InputComp v-model:value="lastName" label="نام خانوادگی" placeholder="نام خانوادگی را وارد کنید" type="text" />
            <InputComp v-model:value="phoneNumber" label="شماره تلفن" placeholder="09012345678 " />
            <InputComp v-model:value="password" label="رمز عبور" placeholder="رمز عبور را وارد کنید" type="password" />
            <InputComp v-model:value="rePassword" label="تکرار رمز عبور" placeholder="رمز عبور را مجدد وارد کنید" type="password" />
            <div class="submit">
              <ButtonComp label="ثبت نام" color="blue" @click="submitForm" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ButtonComp from './components/ButtonComp.vue';
import InputComp from './components/InputComp.vue';
export default {
  name: 'App',
  components: { InputComp, ButtonComp },
  data() {
    return {
      firstName: '',
      lastName: '',
      phoneNumber: '',
      password: '',
      rePassword: '',
    };
  },
  methods: {
    submitForm() {
      if (this.password !== this.rePassword) {
        alert("رمز عبور با تکرار آن مطابقت ندارد.");
      } else {
        alert(this.firstName + ' عزیز، حساب کاربری شما با موفقیت ایجاد شد!');
      }
    }
  },
};
</script>

<style>
body {
  margin: 0;
  background-color: #f1f1f1;
  font-family: 'Vazirmatn', sans-serif;
}

.form-page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #eaf6ff;
  width: 100%;
}

.container {
  width: 100%;
  max-width:700px;
  padding: 0 20px;
  box-sizing: border-box;
}


.background {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #e0f2ff, #f5fbff);
  display: flex;
  justify-content: center;
  align-items: center;
}

.form-wrapper {
  width: 100%;
  max-width: none;
  margin: 0 auto;
}

.form-container {
  width: 100%;
  background-color: white;
  padding: 40px;
  border-radius: 16px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
}

.input-group {
  margin-bottom: 20px;
}

.form-label {
  font-weight: 600;
  font-size: 14px;
  margin-bottom: 5px;
  color: #333;
}

.form-input {
  padding: 12px 16px;
  font-size: 15px;
  border-radius: 10px;
  border: 1px solid #ccc;
  transition: all 0.3s;
}

.form-input:focus {
  border-color: #4f8ef7;
  box-shadow: 0 0 0 3px rgba(79, 142, 247, 0.2);
  outline: none;
}

button {
  background: linear-gradient(to left, #4f8ef7, #00c6ff);
  border: none;
  color: white;
  padding: 12px 30px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 25px;
  cursor: pointer;
  transition: 0.3s ease;
}

button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(0, 198, 255, 0.25);
}

.submit {
  text-align: center;
  margin-top: 25px;
}

.welcome-msg {
  margin-top: 20px;
  background-color: #e6faff;
  color: #055160;
  padding: 15px;
  border-radius: 12px;
  font-weight: bold;
  text-align: center;
  font-size: 15px;
  box-shadow: 0 5px 15px rgba(0, 198, 255, 0.1);
}
</style>