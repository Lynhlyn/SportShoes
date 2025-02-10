<script setup>
import { useRouter } from 'vue-router';

const props = defineProps({
  titleHeader: {
    type: String,
    required: true,
    default: 'SportShoes',
  },
});

const router = useRouter();

// Handle logout and redirect to the login page
const handleLogout = () => {
  localStorage.removeItem("userLogin");
  router.push('/login');
};
</script>

<template>
  <div class="container-fluid bg-primary d-flex align-items-center justify-content-between px-4" style="height: 100px;">
    <!-- Logo & Title -->
    <div class="d-flex align-items-center">
      <img src="/src/assets/logo/logo2.png" alt="Logo" class="logo me-3" />
      <h3 class="text-light mb-0">{{ props.titleHeader }}</h3>
    </div>

    <!-- Đăng xuất -->
    <button @click="handleLogout" class="btn btn-light fw-bold">Đăng xuất</button>
  </div>
</template>

<style scoped>
.logo {
  height: 60px;
  width: auto;
  object-fit: contain;
}
</style>
