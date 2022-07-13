<script setup lang="ts">
import { Button as KButton } from "@progress/kendo-vue-buttons";
import { Popup as KPopup } from "@progress/kendo-vue-popup";

import { ref } from "vue";

const showTeams = ref(false);
</script>
<template>
  <div class="p-4 border-bottom"></div>

  <button ref="button" @click="showTeams" class="btn btn-primary">
    <span class="k-icon k-i-ungroup"></span>"""
  </button>

  <KPopup></KPopup>

  <KButton
    theme-color="secondary"
    :rounded="'full'"
    :icon="'logout'"
    :shape="'rectangle'"
    >Logout
  </KButton>
</template>
