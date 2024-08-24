<template>
  <div class="login-container">
    <div class="login-box">
      <div class="logo">Logo</div>
      <div class="login-fields">
        <input type="text" placeholder="Kullanıcı Adı" v-model="username" />
        <input type="password" placeholder="Şifre" v-model="password" />
      </div>
      <div class="options">
        <label>
          <input type="checkbox" v-model="rememberMe" />
          Beni Hatırla
        </label>
        <a href="#" class="forgot-password">Şifremi Unuttum</a>
      </div>
      <button @click="login" class="login-button">GİRİŞ</button>
      <div class="social-login">
        <button @click="loginWithGoogle" class="google">Google ile Giriş Yap</button>
        <button @click="loginWithFacebook" class="facebook">Facebook ile Giriş Yap</button>
      </div>
      <div class="signup">
        <a href="#">Hesabın yok mu? Kayıt ol</a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { useRouter } from 'vue-router';

export default defineComponent({
  setup() {
    const username = ref('');
    const password = ref('');
    const rememberMe = ref(false);
    const router = useRouter();

    const login = () => {
      if (username.value === 'admin' && password.value === 'password') {
        router.push('/dashboard');
      } else {
        alert('Geçersiz kullanıcı adı veya şifre');
      }
    };

    const loginWithGoogle = () => {
      console.log('Google ile giriş yapılıyor...');
    };

    const loginWithFacebook = () => {
      console.log('Facebook ile giriş yapılıyor...');
    };

    return {
      username,
      password,
      rememberMe,
      login,
      loginWithGoogle,
      loginWithFacebook,
    };
  },
});
</script>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: #f0f2f5;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f2f5;
}

.login-box {
  background: white;
  padding: 40px;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
  text-align: center;
}

.logo {
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 30px;
  color: #34495e;
}

.login-fields input[type="text"],
.login-fields input[type="password"] {
  width: 100%;
  padding: 15px;
  margin: 10px 0;
  border-radius: 8px;
  border: 1px solid #ccc;
  background-color: #fafafa;
  font-size: 16px;
  box-sizing: border-box;
}

.login-button {
  width: 100%;
  padding: 15px;
  margin: 20px 0;
  background-color: #34495e;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.login-button:hover {
  background-color: #2c3e50;
}

.options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 15px 0;
}

.social-login {
  margin: 20px 0;
}

.social-login button {
  width: 100%;
  padding: 12px;
  margin: 8px 0;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
}

.social-login .google {
  background-color: #ea4335;
  color: white;
}

.social-login .facebook {
  background-color: #3b5998;
  color: white;
}

a {
  color: #3498db;
  text-decoration: none;
  font-size: 14px;
}

.signup a {
  font-weight: bold;
}

@media (max-width: 768px) {
  .login-box {
    padding: 20px;
    width: 90%;
  }

  .login-fields input[type="text"],
  .login-fields input[type="password"] {
    padding: 12px;
    font-size: 14px;
  }

  .login-button,
  .social-login button {
    padding: 12px;
  }

  .logo {
    font-size: 24px;
  }
}
</style>