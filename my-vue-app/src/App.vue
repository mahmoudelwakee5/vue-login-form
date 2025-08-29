<template>
  <div class="container">
    <div class="login-box">
      <h2>تسجيل الدخول</h2>
      <img src="./assets/vue.svg" />
      <form @submit.prevent="login">
        <div class="input-box">
          <label>البريد الإلكتروني</label>
          <input v-model="email" type="email" placeholder="example@mail.com" />
        </div>

        <div class="input-box">
          <label>كلمة المرور</label>
          <input v-model="password" type="password" placeholder="••••••••" />
        </div>

        <button type="submit">دخول</button>
      </form>
      <p class="register-text">
        ليس لديك حساب؟
        <a href="#">سجل الآن</a>
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"

const email = ref("")
const password = ref("")

const login = () => {
  if (!email.value || !password.value) {
    alert("من فضلك املأ كل البيانات")
  } else {
    alert(`تم تسجيل الدخول بالبريد: ${email.value}`)
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(to right, #7b2ff7, #f107a3);
}

.login-box {
  background: #fff;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 8px 25px rgba(0,0,0,0.2);
  width: 100%;
  max-width: 350px;
  text-align: center;
}

.login-box h2 {
  margin-bottom: 20px;
  color: #333;
}

.input-box {
  text-align: left;
  margin-bottom: 15px;
}

.input-box label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  color: #444;
}

.input-box input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 8px;
  outline: none;
  transition: border 0.3s;
}

.input-box input:focus {
  border-color: #7b2ff7;
}

button {
  width: 100%;
  padding: 12px;
  background: #7b2ff7;
  color: #fff;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #5a1bcc;
}

.register-text {
  margin-top: 15px;
  font-size: 14px;
}

.register-text a {
  color: #7b2ff7;
  text-decoration: none;
  font-weight: bold;
}

.register-text a:hover {
  text-decoration: underline;
}
</style>
