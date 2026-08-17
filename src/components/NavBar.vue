<script setup>
const links = [
  { href: '#about', label: 'about' },
  { href: '#experience', label: 'experience' },
  { href: '#education', label: 'education' },
  { href: '#skills', label: 'skills' },
  { href: '#contact', label: 'contact' },
]
</script>

<template>
  <nav>
    <div class="nav-inner">
      <div class="nav-logo">ra_tithdavid.dev</div>
      <div class="nav-links">
        <a v-for="link in links" :key="link.href" :href="link.href">{{ link.label }}</a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
nav{
  position:sticky;
  top:0;
  z-index:10;
  backdrop-filter:blur(10px);
  background:rgba(15,20,32,0.85);
  border-bottom:1px solid var(--line);
}
.nav-inner{
  max-width:920px;
  margin:0 auto;
  padding:16px 24px;
  display:flex;
  align-items:center;
  justify-content:space-between;
}
.nav-logo{
  font-family:var(--mono);
  font-size:14px;
  color:var(--amber);
  letter-spacing:0.02em;
}
.nav-links{
  display:flex;
  gap:24px;
  font-family:var(--mono);
  font-size:13px;
  color:var(--muted);
}
.nav-links a{
  text-decoration:none;
  transition:color 0.2s;
}
.nav-links a:hover{color:var(--amber);}

@media (max-width:640px){
  .nav-links{gap:12px; font-size:10.5px;}
  .nav-inner{padding:14px 16px;}
}
@media (max-width:400px){
  .nav-links{gap:8px; font-size:9.5px;}
}
</style>
