<template>
  <div class="login-view">
    <!-- 登录背景 -->
    <div class="login-bg" :class="isInputFocus ? 'login-bg-blur' : ''"></div>
    <!-- 登录表单 -->
    <div class="login-contain">
      <div class="login-content">
        <div class="login-form">
          <h2>登 录</h2>
          <div class="login-input-group">
            <i class="el-icon-user"></i>
            <input
              @focus="inputFocus"
              @blur="inputBlur"
              v-model="userName"
              type="text"
              autocomplete="off"
              placeholder="请输入邮箱、用户名、账号"
            />
          </div>
          <div class="login-input-group">
            <i class="el-icon-lock"></i>
            <input
              @focus="inputFocus"
              @blur="inputBlur"
              v-model="password"
              :type="passwordInpType"
              autocomplete="off"
              placeholder="请输入密码"
            />
            <span
              @click="viewPassWord"
              :class="['el-icon-view', pwdActive ? 'pwd-active' : '']"
            ></span>
          </div>
          <input @click="loginHandler" type="button" class="login-dfbtn" value="登 录" />
          <div @click="forgetPassword" class="login-else"><a>忘记密码？</a></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'LoginView',
  data() {
    return {
      userName: '', // 用户名
      password: '', // 密码
      isInputFocus: false, // 输入框是否聚焦
      passwordInpType: 'password' // 密码输入框的type类型
    };
  },
  computed: {
    /**
     * 是否正在输入密码
     */
    pwdActive() {
      return this.password !== '';
    }
  },
  methods: {
    /**
     * 输入框获取到焦点
     */
    inputFocus() {
      this.isInputFocus = true;
    },
    /**
     * 输入框失去到焦点
     */
    inputBlur() {
      this.isInputFocus = false;
    },
    /**
     * 查看/隐藏密码
     */
    viewPassWord() {
      this.passwordInpType === 'password'
        ? (this.passwordInpType = 'text')
        : (this.passwordInpType = 'password');
    },
    /**
     * 校验账号密码
     */
    verify() {
      if (this.userName === 'admin' && this.password === '123') {
        return true;
      } else {
        return false;
      }
    },
    /**
     * 点击登录
     */
    loginHandler() {
      console.log(this.userName, this.password);
      if (this.verify()) {
        // 验证成功，跳转到首页
        this.$router.push('/home');
      } else {
        this.$notify.error({
          title: '错误',
          duration: 2500,
          message: '您输入的账号或密码错误!'
        });
      }
    },
    /**
     * 定义忘记密码提示语
     */
    defineMessage() {
      const h = this.$createElement;
      return h('div', null, [
        h('div', null, '默认用户名为: admin;'),
        h('div', { style: 'margin-top: 15px' }, '默认密码为: 123。')
      ]);
    },
    /**
     * 忘记密码
     */
    forgetPassword() {
      this.$alert(this.defineMessage(), '系统提示', {
        confirmButtonText: '我知道了',
        callback: () => {}
      });
    }
  }
};
</script>
<style lang="scss">
.login-view {
  position: relative;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  height: 100%;
  overflow: hidden;
  .login-bg {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background-image: url('../assets/img/login-bg.jpg');
    transition: all 0.5s;
  }
  .login-bg-blur {
    background-image: url('../assets/img/login-bg-blur.jpg');
  }
  .login-contain {
    position: relative;
    width: 400px;
    height: 430px;
    margin-right: 6%;
    background: #fff;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 20px 40px #0a6b6033;
    .login-content {
      display: flex;
      width: 100%;
      height: 100%;
      float: left;
      position: relative;
      justify-content: center;
      align-items: center;
      .login-form {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        box-sizing: border-box;
        width: 100%;
        height: max-content;
        padding: 0 40px;
        h2 {
          font-size: 36px;
          font-weight: 500;
        }
        .login-input-group {
          position: relative;
          display: flex;
          justify-content: flex-start;
          align-items: center;
          width: 100%;
          height: 40px;
          margin-top: 30px;
          overflow: hidden;
          background: #f4f4f4;
          border-radius: 5px;
          .el-icon-view {
            display: none;
            position: absolute;
            right: 0;
            bottom: 0;
            width: 37px;
            height: 37px;
            justify-content: center;
            align-items: center;
            cursor: pointer;
          }
          .pwd-active {
            display: flex;
          }
          i {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            border-radius: 5px;
            background: #08d9d6;
            color: #fff;
            font-weight: 800;
          }
          input {
            flex: 1;
            height: 100%;
            color: #495057;
            border: none;
            padding: 0 10px;
            box-sizing: border-box;
            line-height: 1.5;
            outline: none !important;
            background: transparent;
          }
        }
        .login-dfbtn {
          box-sizing: border-box;
          display: block;
          width: 100%;
          height: 38px;
          border: none;
          border-radius: 5px;
          text-align: center;
          color: #fff;
          cursor: pointer;
          font-size: 18px;
          background: #08d9d6;
          margin-top: 30px;
        }
        .login-else {
          width: 100%;
          text-align: center;
          font-size: 16px;
          cursor: pointer;
          margin-top: 10px;
          a {
            color: #08d9d6;
          }
        }
      }
    }
  }
}
</style>
