<template lang="">
    <div>
        <div class="row">
            <div class="col-md-6 mx-auto">
                <form @submit.prevent="submit()">
                    <fieldset>
                        <h1>Signin</h1>
                        <div class="form-group">
                            <label for="email">Email address</label>
                            <input v-model="user.email" type="email" class="form-control" id="email" aria-describedby="emailHelp"
                                placeholder="Enter email">
                        </div>
                        <div class="form-group">
                            <label for="password">Password</label>
                            <input v-model="user.password" type="password" class="form-control" id="password" placeholder="Password">
                        </div>
                        <div class="form-group">
                            <button type="submit" class="btn btn-primary btn-block">Sign In</button>
                        </div>
                    </fieldset>
                </form>
            </div>
        </div>
    </div>
</template>
<script>
    import {
        mapActions
    } from 'vuex'
    export default {
        data() {
            return {
                user: {
                    email: '',
                    password: ''
                }
            }
        },
        methods: {
            ...mapActions({
                'signIn': 'auth/signIn'
            }),
            submit() {
                this.signIn(this.user).then(
                    () => this.$router.replace({
                        name: 'Dashboard'
                    })
                )
            }
        },
    }
</script>
<style lang="">

</style>