<script setup>
const skillGroups = [
  { title: 'Languages & Markup', items: ['Python', 'HTML', 'CSS', 'Tailwind CSS'] },
  { title: 'Frameworks', items: ['Vue.js', 'Angular', 'Frappe'] },
  { title: 'Practice', items: ['UI/UX', 'Research', 'Networking', 'Computer Hardware'] },
]
</script>

<template>
  <section class="section fade-up" id="skills">
    <div class="section-head">
      <span class="section-path">~/skills</span>
      <h2 class="section-title">Skills</h2>
    </div>
    <div class="skill-groups">
      <div class="skill-group" v-for="(g, i) in skillGroups" :key="i">
        <h4>{{ g.title }}</h4>
        <div class="chip-row">
          <span class="chip" v-for="(item, j) in g.items" :key="j">{{ item }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skill-groups{
  display:grid;
  grid-template-columns:repeat(auto-fit, minmax(220px,1fr));
  gap:16px;
}
.skill-group{
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:8px;
  padding:16px 18px;
}
.skill-group h4{
  margin:0 0 12px;
  font-family:var(--mono);
  font-size:12px;
  color:var(--amber);
  text-transform:uppercase;
  letter-spacing:0.06em;
}
.chip-row{display:flex; flex-wrap:wrap; gap:8px;}
.chip{
  font-family:var(--mono);
  font-size:12.5px;
  padding:5px 10px;
  border:1px solid var(--line);
  border-radius:5px;
  color:var(--text);
}
</style>
