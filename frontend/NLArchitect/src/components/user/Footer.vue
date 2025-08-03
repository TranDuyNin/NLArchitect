<template>
  <footer class="site-footer">
    <div class="footer-content">
      <div class="footer-left">
        <p>&copy; 2025 Huni Architectes</p>
      </div>
      <div class="footer-right">
        <a href="#">Facebook</a>
        <a href="#">LinkedIn</a>
        <a href="#">Contact</a>
      </div>
    </div>
  </footer>
</template>

<script setup>
// Không cần logic JS cho footer tĩnh
</script>

<style scoped>
.site-footer {
  background-color: black;
  color: white;
  padding: 30px 20px;
  text-align: center;
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 10px;
  align-items: center;
  justify-content: space-between;
}

.footer-left p {
  margin: 0;
  font-size: 14px;
  opacity: 0.6;
}

.footer-right {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.footer-right a {
  color: white;
  font-size: 14px;
  text-decoration: none;
  opacity: 0.8;
  transition: opacity 0.3s;
}

.footer-right a:hover {
  opacity: 1;
}

@media (min-width: 768px) {
  .footer-content {
    flex-direction: row;
  }
}
</style>
