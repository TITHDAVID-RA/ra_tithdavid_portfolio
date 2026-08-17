<script setup>
const education = [
  {
    title: 'Computer Science',
    org: 'Norton University',
    period: '2023 — Present',
    status: 'active',
  },
  {
    title: 'Diploma',
    org: 'Mahasastra School',
    period: '2020 — 2023',
    status: 'past',
  },
  {
    title: 'GEP 12 Graduate',
    org: 'Australian Centre for Education (ACE)',
    period: '2026',
    status: 'past',
  },
]
</script>

<template>
  <section class="section fade-up" id="education">
    <div class="section-head">
      <span class="section-path">~/education</span>
      <h2 class="section-title">Education</h2>
    </div>

    <div class="record" v-for="(ed, i) in education" :key="i">
      <div class="record-head">
        <div>
          <div class="record-title">{{ ed.title }}</div>
          <div class="record-sub">{{ ed.org }}</div>
        </div>
        <span class="record-badge">{{ ed.status === 'active' ? '● in progress' : ed.period }}</span>
      </div>
    </div>
  </section>
</template>
