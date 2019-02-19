<script>
import CcUsers from './components/users/main.vue'
import { mapState, mapActions } from "vuex";

export default {
  name: 'CodecastApp',
  mounted() {
    const payload = {
      name: 'Alvaro Luiz',
      email: 'alvaro@luiz.com',
      level: 'admin',
      city: 'Brasilia',
      state: 'DF'
    }

    setTimeout(() => {
      this.changeUser(payload)
      /* this.$store.dispatch('changeUser',
        payload) */
    }, 2000)

  },
  components: {
    CcUsers
  },
  methods: {
    ...mapActions(['changeUser'])
  },
  computed:{
    ...mapState({
      user: state => {
        const { name, email } = state.user
        return `User logged is ${name} and h
                as the email ${email}`
      }
    })
  }
}
</script>

<template>
  <div>
    <h1>Wellcome Vue2</h1>
    <h4>{{ user }}</h4>
    <hr>
    <cc-users></cc-users>
  </div>
</template>

