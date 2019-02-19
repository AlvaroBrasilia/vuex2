<script>
import { mapActions } from 'vuex';
export default {
    methods: {
        changeData () {
            const payload = {
                name: 'Other Name',
                email: 'other@email.com',
                level: 'other-level',
                city: 'Other City',
                state: 'Other State'
            }
            this.changeUser(payload)
        },
        ...mapActions(['changeUser'])
    },
    computed: {
        hasUser() {
            return this.$store.state.user.name !== ''
        }
    }
}
</script>


<template>
    <div>
        <button :disabled="!hasUser" @click="changeData">Change data user</button>
    </div>
</template>
