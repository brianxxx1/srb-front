<template>
  <div class="personal-main">
    <div class="personal-pay">
      <h3><i>Register A Third Party Account</i></h3>
      <div class="pay-notice">
        <p>
          Please open HFB account to continue
        </p>
      </div>
      <div class="pay-form">
        <ul>
          <li>
            <label>Legal Name</label>
            <input
              v-model="userBind.name"
              type="text"
              class="pay-txt"
              maxlength="16"
              placeholder="Your real name"
            />
          </li>
          <li>
            <label>ID Number</label>
            <input
              v-model="userBind.idCard"
              type="text"
              class="pay-txt"
              maxlength="18"
              placeholder="Your ID Number"
            />
            <div id="idCardErrorDiv">
              <p style="margin-top:10px;">
                The ID information cannot be modified afterwards, be careful
              </p>
            </div>
          </li>
          <li>
            <label>Bank Name</label>
            <input
              v-model="userBind.bankType"
              type="text"
              class="pay-txt"
              placeholder="Bank Name"
            />
          </li>
          <li>
            <label>Card No</label>
            <input
              v-model="userBind.bankNo"
              type="text"
              class="pay-txt"
              placeholder="Your Card Number"
            />
          </li>
          <li>
            <label>Phone</label>
            <input
              v-model="userBind.mobile"
              type="text"
              class="pay-txt"
              placeholder="Phone Number"
            />
          </li>
          <li>
            <label>&nbsp;</label>
            <input v-model="agree" type="checkbox" />

            I have read and agree
            <a href="#" class="c-orange" target="_blank">
              "HFB Custody Account Agreement"
            </a>
          </li>
          <li>
            <label>&nbsp;</label>
            <el-button :disabled="!agree" @click="commitBind()" type="primary">
              Register
            </el-button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      agree: false,
      userBind: {},
    };
  },

  methods: {
    commitBind() {
      this.$alert(
        '<div style="size: 18px;color: red;">You are about to go to HFB to bind your account</div>',
        "Go to HFB platform",
        {
          dangerouslyUseHTMLString: true,
          confirmButtonText: "GO",
          callback: (action) => {
            if (action === "confirm") {
              this.$axios
                .$post("api/core/userBind/auth/bind", this.userBind)
                .then((response) => {
                  document.write(response.data.formStr);
                });
            }
            //TODO 提交用户信息
          },
        }
      );
    },
  },
};
</script>
