<template lang="">
    <div>
        <h1>Dashboard</h1>
    </div>
</template>
<script>
    import store from '@/store'

    export default {
        beforeRouteEnter(to, from, next) {
            if (!store.getters['auth/authenticated']) {
                next({
                    name: 'Signin'
                })
            } else {
                next()
            }
        }
    }
</script>
<style lang="">

</style>