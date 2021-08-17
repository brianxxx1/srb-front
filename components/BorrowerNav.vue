<template>
  <ul>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user' }">
      <span>
        <NuxtLink to="/user">
          <i class="dot dot1"></i>Account Overview</NuxtLink
        >
      </span>
    </li>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user/fund' }">
      <span>
        <NuxtLink style="text-align:center;width:115px;" to="/user/fund">
          Amount Record
        </NuxtLink>
      </span>
    </li>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user/invest' }">
      <span>
        <NuxtLink style="text-align:center;width:115px;" to="/user/invest">
          Borrow Record
        </NuxtLink>
      </span>
    </li>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user/payment' }">
      <span>
        <NuxtLink style="text-align:center;width:115px;" to="/user/payment">
          Return Plan
        </NuxtLink>
      </span>
    </li>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user/recharge' }">
      <span
        ><NuxtLink to="/user/recharge"
          ><i class="dot dot03"></i>Pop Up</NuxtLink
        ></span
      >
    </li>
    <li :class="{ 'pleft-cur': $route.fullPath === '/user/withdraw' }">
      <span
        ><NuxtLink to="/user/withdraw"
          ><i class="dot dot04"></i>Withdraw</NuxtLink
        ></span
      >
    </li>
  </ul>
</template>

<script>
export default {};
</script>
