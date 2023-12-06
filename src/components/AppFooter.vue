<template>
  <CFooter class="px-4">
    <div>
      <a href="https://www.theeaeye.com/" target="_blank">EA-EYE</a>
      <span class="ms-1"
        >&copy; {{ new Date().getFullYear() }} East African Eye</span
      >
    </div>
    <div class="ms-auto">
      <span class="me-1" target="_blank">Powered by</span>
      <a href="https://www.theeaeye.com/">Lighthouse Sports</a>
    </div>
  </CFooter>
</template>

<script>
export default {
  name: 'AppFooter',
}
</script>
