<script setup lang="ts">
import { isInPopup } from '~/logic/state'
</script>

<template>
  <div>
    <div px3 py2 border="b base" flex="~ gap-2">
      <PopupButton v-if="!isInPopup" />
      <VDDarkToggle v-slot="{ toggle, isDark }">
        <VDButton n="sm primary" @click="toggle">
          <div carbon-sun translate-y--1px dark:carbon-moon />
          {{ isDark.value ? "Dark" : "Light" }}
        </VDButton>
      </VDDarkToggle>
      <RouterLink
        replace
        class="n-button-base active:n-button-active focus-visible:n-focus-base n-transition n-primary n-sm hover:n-button-hover n-disabled:n-disabled"
        to="/settings"
      >
        <div carbon-settings translate-y--1px />
        Settings
      </RouterLink>
    </div>
  </div>
</template>
