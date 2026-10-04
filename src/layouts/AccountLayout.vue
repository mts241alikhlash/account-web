<script setup lang="ts">
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import { Button } from '@mts241alikhlash/ui/button'
import { authService, useAuthStore, useSsoApps } from '@/features/platform/auth'

const route = useRoute()
const store = useAuthStore()
const { apps, load } = useSsoApps()
void load()

const backTo = computed(() =>
  apps.value.find((app) => app.key === route.query.from),
)

async function logout() {
  await authService.logoutUser()
  window.location.assign('/login')
}
</script>

<template>
  <div class="min-h-svh bg-muted/30">
    <header class="flex items-center gap-4 border-b bg-background px-6 py-3">
      <span class="font-semibold">241 Akun</span>
      <RouterLink
        to="/"
        class="text-sm"
      >
        Aplikasi
      </RouterLink>
      <RouterLink
        to="/profile"
        class="text-sm"
      >
        Profil
      </RouterLink>
      <a
        v-if="backTo"
        :href="backTo.url"
        class="text-sm"
      >
        Kembali ke {{ backTo.label }}
      </a>
      <div class="ml-auto flex items-center gap-3">
        <span class="text-sm text-muted-foreground">
          {{ store.user?.identifier }}
        </span>
        <Button
          variant="outline"
          size="sm"
          @click="logout"
        >
          Keluar
        </Button>
      </div>
    </header>
    <RouterView />
  </div>
</template>
