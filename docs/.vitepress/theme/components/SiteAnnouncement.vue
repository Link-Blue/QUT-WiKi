<script setup lang="ts">
import { computed } from 'vue'
import { siteAnnouncement } from '../announcement'

const visible = computed(() => siteAnnouncement.message.trim().length > 0)
</script>

<template>
  <div
    v-if="visible"
    class="site-announcement"
    role="status"
    :style="{
      '--announcement-background': siteAnnouncement.background,
      '--announcement-color': siteAnnouncement.color,
    }"
  >
    <span class="site-announcement-message">{{ siteAnnouncement.message }}</span>
  </div>
</template>
