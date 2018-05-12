<template>
  <div class="admin">
    <h1>Admin Main Page</h1>
    <h1>welcome {{userId}}</h1>
    <a href="#" @click="quit">注销登录</a>
  </div>
</template>

<script type="text/ecmascript-6">
import {getCookie, delCookie} from '@/common/js/cookie.js'
export default {
  name: 'admin',
  data () {
    return {
      userId: ''
    }
  },
  created () {
    let uname = getCookie('AdminId')
    console.log('uname', uname)
    this.userId = uname
    if (uname === '') {
      this.$router.push('/')
    }
  },
  methods: {
    quit () {
      delCookie('AdminId')
      this.$router.push('/')
    }
  }
}
</script>

<style lang="stylus" ref="stylesheet/stylus">
</style>
