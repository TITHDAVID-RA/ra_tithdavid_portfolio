<script setup>
import { ref, onMounted } from 'vue'
import davidPhoto from '../assets/david.jpg'

const typedLines = ref([])

const bootLines = [
  { type: 'cmd', text: 'whoami' },
  { type: 'out', label: 'name', value: 'Ra Tithdavid' },
  { type: 'out', label: 'role', value: 'Web Developer' },
  { type: 'out', label: 'based_in', value: 'Phnom Penh, Cambodia' },
  { type: 'out', label: 'status', value: 'open to opportunities' },
]

onMounted(() => {
  let i = 0
  const reveal = () => {
    if (i < bootLines.length) {
      typedLines.value.push(bootLines[i])
      i++
      setTimeout(reveal, i === 1 ? 500 : 260)
    }
  }
  reveal()
})
</script>

<template>
  <section class="hero">
    <div class="hero-grid">
      <div class="terminal">
        <div class="term-bar">
          <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
          <span class="term-title">~/portfolio — zsh</span>
        </div>
        <div class="term-body">
          <template v-for="(line, i) in typedLines" :key="i">
            <div v-if="line.type === 'cmd'">
              <span class="prompt">david@dev</span><span class="out-label">:~$ </span><span class="cmd">{{ line.text }}</span>
            </div>
            <div v-else>
              <span class="out-label">{{ line.label }}:</span> <span class="out-value">{{ line.value }}</span>
            </div>
          </template>
          <span class="cursor"></span>
        </div>
      </div>

      <div class="photo-frame">
        <img :src="davidPhoto" alt="Portrait of Ra Tithdavid" />
      </div>
    </div>

    <div class="hero-role">
      <h1 class="hero-name">Building systems<br />that hold up.</h1>
      <p class="hero-tag">
        Web developer specializing in Frappe backend architecture, Angular &amp; Vue frontends,
        and the automation in between. Based in Phnom Penh, Cambodia.
      </p>
      <div class="hero-cta">
        <a class="btn primary" href="#experience">view experience</a>
        <a class="btn ghost" href="#contact">get in touch</a>
        <a class="btn ghost" href="https://tithdavid-ra.github.io/ONE_SHOT-2.0/" target="_blank" rel="noopener">github project ↗</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero{
  padding:64px 0 60px;
}
.hero-grid{
  display:grid;
  grid-template-columns:1fr auto;
  gap:24px;
  align-items:stretch;
}
.terminal{
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:10px;
  overflow:hidden;
  box-shadow:0 20px 60px -20px rgba(0,0,0,0.6);
  min-width:0;
}
.term-bar{
  display:flex;
  align-items:center;
  gap:8px;
  padding:10px 14px;
  background:var(--ink-2);
  border-bottom:1px solid var(--line);
}
.dot{width:10px;height:10px;border-radius:50%;}
.dot.r{background:#e0645c;}
.dot.y{background:#e5c065;}
.dot.g{background:#65c088;}
.term-title{
  margin-left:8px;
  font-family:var(--mono);
  font-size:12px;
  color:var(--muted);
}
.term-body{
  padding:28px 24px 32px;
  font-family:var(--mono);
  font-size:14px;
  line-height:1.8;
  min-height:220px;
}
.prompt{color:var(--green);}
.cmd{color:var(--text);}
.out-label{color:var(--muted);}
.out-value{color:var(--amber);}
.cursor{
  display:inline-block;
  width:8px;height:16px;
  background:var(--amber);
  vertical-align:middle;
  animation:blink 1s step-end infinite;
}
@keyframes blink{50%{opacity:0;}}

.photo-frame{
  width:220px;
  border:1px solid var(--line);
  border-radius:10px;
  background:var(--panel);
  padding:8px;
  display:flex;
  align-items:flex-end;
  justify-content:center;
  overflow:hidden;
  box-shadow:0 20px 60px -20px rgba(0,0,0,0.6);
}
.photo-frame img{
  width:100%;
  height:100%;
  object-fit:cover;
  border-radius:6px;
  filter:grayscale(15%) contrast(1.03);
}

.hero-role{margin-top:28px;}
.hero-name{
  font-size:clamp(32px,7vw,64px);
  font-weight:800;
  letter-spacing:-0.02em;
  line-height:1.05;
  margin:0;
}
.hero-tag{
  margin-top:10px;
  color:var(--muted);
  font-size:16px;
  max-width:560px;
  line-height:1.6;
}
.hero-cta{
  margin-top:26px;
  display:flex;
  gap:14px;
  flex-wrap:wrap;
}

@media (max-width:720px){
  .hero-grid{
    grid-template-columns:1fr;
  }
  .photo-frame{
    width:100%;
    max-width:260px;
    margin:0 auto;
    aspect-ratio:3/4;
  }
}
@media (max-width:480px){
  .term-body{padding:22px 16px 26px; font-size:13px;}
  .hero-cta{gap:10px;}
  .btn{font-size:12px; padding:10px 16px;}
}
</style>
