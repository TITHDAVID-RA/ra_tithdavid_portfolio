<script setup>
</script>

<template>
  <section class="section fade-up" id="contact">
    <div class="section-head">
      <span class="section-path">~/contact</span>
      <h2 class="section-title">Contact</h2>
    </div>
    <div class="contact-panel">
      <h3>Let's build something.</h3>
      <p>Open to web development roles and freelance projects.</p>
      <div class="contact-links">
        <a class="btn primary" href="mailto:rtithdavid@gmail.com">rtithdavid@gmail.com</a>
        <a class="btn ghost" href="tel:+85589912457">+855 89 912 457</a>
        <a class="btn ghost" href="https://tithdavid-ra.github.io/ONE_SHOT-2.0/" target="_blank" rel="noopener">github ↗</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-panel{
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:10px;
  padding:32px 28px;
  text-align:center;
}
.contact-panel h3{
  font-size:24px;
  margin:0 0 10px;
}
.contact-panel p{
  color:var(--muted);
  margin:0 0 22px;
  font-size:14.5px;
}
.contact-links{
  display:flex;
  gap:14px;
  justify-content:center;
  flex-wrap:wrap;
}

@media (max-width:480px){
  .contact-panel{padding:26px 18px;}
  .contact-links{flex-direction:column; align-items:stretch;}
  .contact-links .btn{justify-content:center;}
}
</style>
