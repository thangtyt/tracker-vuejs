<template>
    <div>
        <h1>
            Register
        </h1>
        <input
            type="text"
            name="email"
            placeholder="E-Mail"
            v-model="email"
            />
        <br>
        <input
            type="password"
            name="password"
            placeholder="Password"
            v-model="password"
            />
            <br>
        <button
        @click="register">Register</button>
    </div>
</template>
<script>
import AuthService from '@/services/AuthService'
export default {
  data () {
    return {
      email: 'thangnv@mcbooks.vn',
      password: '12345678'
    }
  },
  methods: {
    async register () {
      const res = await AuthService.register({
        email: this.email,
        password: this.password
      })
      console.log(res.data)
    }
  }
}
</script>
<style scoped>
</style>
