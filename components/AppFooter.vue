<template>
  <!--网站底部-->
  <div id="footer" class="ft">
    <div class="ft-inner clearfix">
      <div class="ft-helper clearfix">
        <dl>
          <dt>About Us</dt>
          <dd>
            <NuxtLink to="/about/profile">Company</NuxtLink
            ><NuxtLink to="/about/leader">Team</NuxtLink
            ><NuxtLink to="/about/report">Announcements</NuxtLink>
          </dd>
        </dl>
        <dl>
          <dt>Service</dt>
          <dd>
            <NuxtLink to="/invest">Investment</NuxtLink
            ><NuxtLink to="/borrow">Return</NuxtLink>
          </dd>
        </dl>
        <dl>
          <dt>Help Center</dt>
          <dd>
            <NuxtLink to="/help">Intro</NuxtLink
            ><NuxtLink to="/user">My Account</NuxtLink>
          </dd>
        </dl>
        <dl>
          <dt>Contact Us</dt>
          <dd><NuxtLink to="/about">Contact Us</NuxtLink></dd>
        </dl>
      </div>
      <div class="ft-service">
        <dl>
          <dd>
            <p>
              <strong>000-000-0000</strong><br />
              Work Day 9:00-22:00 <br />Saturday 9:00-18:00<br />
            </p>
            <div class="ft-serv-handle clearfix">
              <a
                class="icon-hdSprite icon-ft-sina a-move a-moveHover"
                title="尚融宝新浪微博"
                target="_blank"
                href="#"
              ></a>
              <a
                class="icon-hdSprite icon-ft-qqweibo a-move a-moveHover"
                title="尚融宝腾讯微博"
                target="_blank"
                href="#"
              ></a>
              <a
                class="icon-ft-qun a-move a-moveHover"
                title="尚融宝QQ群"
                target="_blank"
                href="#"
              ></a>
              <a
                class="icon-hdSprite icon-ft-email a-move a-moveHover mrn"
                title="阳光易贷email"
                target="_blank"
                href="mailto:xz@shangrongbao.com"
              ></a>
            </div>
          </dd>
        </dl>
      </div>
      <div class="ft-wap clearfix">
        <dl>
          <dt>QR-Code</dt>
          <dd>
            <span class="icon-ft-erweima">
              <img src="~/assets/images/code.png" style="display: inline;" />
            </span>
          </dd>
        </dl>
      </div>
    </div>
    <div class="ft-record">
      <div class="ft-identity">
        ©2020 SRB All rights reserved&nbsp;&nbsp;&nbsp;
        <span class="color-e6">|</span>&nbsp;&nbsp;&nbsp; Wenshuo's
        Corp&nbsp;&nbsp;&nbsp; <span class="color-e6">|</span>&nbsp;&nbsp;&nbsp;
        <a target="_blank" href="http://www.miitbeian.gov.cn/">
          License:xxxxxxx
        </a>
      </div>
    </div>
  </div>
</template>
