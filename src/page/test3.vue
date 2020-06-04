<template>
  <div class="login_dialog">
    <div class="login_form">
      <div class="login_top">
        <span>请登录</span
        ><i><img src="@/assets/img/icon_close.png" border="none"/></i>
      </div>
      <div class="login_bottom">
        <el-form
          :model="ruleForm"
          :rules="rules"
          ref="ruleForm"
          label-width="90px"
          class="demo-ruleForm"
        >
          <el-form-item label="请输入账号：" prop="identifier">
            <el-input
              type="text"
              v-model="ruleForm.identifier"
              placeholder="请输入账号"
            ></el-input>
          </el-form-item>
          <el-form-item
            label="请输入密码："
            label-width="90px"
            prop="credential"
          >
            <el-input
              type="password"
              v-model="ruleForm.credential"
              placeholder="请输入密码"
              autocomplete="on"
            ></el-input>
          </el-form-item>
          <div class="login_txt">
            <span>登录即代表您已同意</span><a>《用户协议》</a>
          </div>
          <el-form-item>
            <el-button
              type="primary"
              @click="login('ruleForm')"
              class="login_button"
              >立即登录</el-button
            >
          </el-form-item>
        </el-form>
      </div>
    </div>
  </div>
</template>
<script>
import md5 from "js-md5";
import crypto from "crypto";
export default {
  data() {
    return {
      ruleForm: {
        identifier: "",
        credential: ""
      },
      rules: {
        identifier: [
          { required: true, message: "请输入账号", trigger: "blur" },
          { min: 6, max: 64, message: "账号至少6位数", trigger: "blur" }
        ],
        credential: [
          { required: true, message: "请输入密码", trigger: "blur" },
          { min: 6, max: 32, message: "密码至少6位数", trigger: "blur" }
        ]
      }
    };
  },
  mounted() {},
  methods: {
    login(ruleForm) {
      // var that = this;
			// 	let loginParams = { 
		  //      	identifier: this.ruleForm.identifier, //获取账号
		  //      	credential: this.ruleForm.credential //获取密码
      //   };
        this.$api.post('/player', this.ruleForm, response => {
          if (response.status >= 200 && response.status < 300) {
                  console.log(response.data);//请求成功，response为成功信息参数
              } else {
                  console.log(response.message);//求失败，response为失败信息
              }
          });
			
      this.$refs[ruleForm].validate(valid => {

        if (valid) {
        var credential;
        var md5 = crypto.createHash("md5");
        md5.update(ruleForm);
        var credential = md5.digest('hex');
        
        console.log(credential);
          alert("登录成功!");
        } else {
          alert("账号或密码错误！");
          return false;
        }
      });
    }
  }
};
</script>
<style>
body {
  background: none;
}
.login_dialog {
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 0, 0.5);
}
.login_form {
  width: 690px;
  height: 398px;
  margin: 0 auto;
  border: 1px solid teal;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.login_form input:focus {
  border: 1px solid #ccc;
}
.login_top {
  height: 90px;
  line-height: 90px;
  padding: 0 30px;
  overflow: hidden;
  background-color: rgba(242, 242, 242, 1);
  border: 1px solid rgba(255, 255, 255, 0);
  vertical-align: middle;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.login_top span {
  font-size: 20px;
  font-weight: bold;
  color: #333;
  display: inline-block;
  height: 40px;
  line-height: 40px;
  border-bottom: 4px solid #0ba7d4;
  float: left;
}
.login_top i {
  float: right;
}
.login_top i img {
  vertical-align: middle;
  cursor: pointer;
}
.el-form-item.is-required:not(.is-no-asterisk)
  .el-form-item__label-wrap
  > .el-form-item__label:before,
.el-form-item.is-required:not(.is-no-asterisk) > .el-form-item__label:before {
  content: "*";
  color: #f56c6c;
  margin-right: 4px;
  display: none;
}
.login_bottom {
  margin: 30px 0 0 86px;
}
.el-input__inner {
  width: 198px;
  height: 34px;
  background-color: rgba(255, 255, 255, 1);
  text-align: left;
  border: 1px solid rgba(187, 187, 187, 1);
  border-radius: 0;
  margin-left: 36px;
  padding: 0 8px;
  color: #888;
}
.el-input__inner:focus {
  border: 1px solid rgba(11, 167, 212, 1);
}
.login_bottom .login_txt {
  margin-left: 125px;
}
.login_bottom .login_txt span {
  color: rgba(16, 16, 16, 1);
  font-size: 14px;
  text-align: left;
  font-family: SourceHanSansSC-regular;
}
.login_bottom .login_txt a {
  color: rgba(11, 167, 212, 1);
  font-size: 14px;
  text-align: left;
  font-family: SourceHanSansSC-regular;
}
.login_button {
  height: 40px;
  border-radius: 10px;
  background-color: rgba(11, 167, 212, 1);
  text-align: center;
  color: #fff;
  padding: 0 37px;
  box-shadow: 0px 10px 10px -5px rgba(0, 0, 0, 0.1);
  border: 10px solid rgba(255, 255, 255, 0);
  margin-left: 35px;
  margin-top: 50px;
}
.el-form-item__label {
  padding: 0;
}
.login_button span {
  font-size: 16px;
  color: #fff;
}
.el-form-item__error {
  color: red;
  font-size: 12px;
  line-height: 1;
  padding-top: 4px;
  position: absolute;
  top: 100%;
  left: 35px;
}
.login_button:focus,
.login_button:hover {
  background-color: rgba(11, 167, 212, 1) !important;
}
.login_button.is-active,
.login_button:active {
  background-color: rgba(11, 167, 212, 1) !important;
  color: #fff;
}
.el-button--primary.is-active,
.el-button--primary:active {
  background-color: rgba(11, 167, 212, 1) !important;
}
.el-button--primary:focus,
.el-button--primary:hover {
  background-color: rgba(11, 167, 212, 1) !important;
}
.el-button:active {
  background-color: rgba(11, 167, 212, 1) !important;
}
.el-button:focus,
.el-button:hover {
  background-color: rgba(11, 167, 212, 1) !important;
}
</style>
