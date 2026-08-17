<script setup>
const experience = [
  {
    role: 'Web Developer',
    company: 'HRINC (Cambodia) Co., Ltd',
    period: '2024 — 2026',
    status: 'past',
    points: [
      'Architected and customized Frappe-based backend solutions using DocTypes and server-side Python scripts to automate business workflows and data management.',
      'Built dynamic single-page applications (SPA) with custom Angular frontends.',
      'Developed the company\u2019s LMS and HRMS systems on the Frappe framework.',
      'Handled internal IT support: installed software, configured printers and network infrastructure.',
    ],
  },
  {
    role: 'IT Support & Computer Repair (Part-time)',
    company: 'Quick Fix',
    period: '2025 — Present',
    status: 'active',
    points: [
      'Install and configure computer hardware.',
      'Set up and troubleshoot software for client machines.',
    ],
  },
]
</script>

<template>
  <section class="section fade-up" id="experience">
    <div class="section-head">
      <span class="section-path">~/experience</span>
      <h2 class="section-title">Work Experience</h2>
    </div>

    <div class="record" v-for="(job, i) in experience" :key="i">
      <div class="record-head">
        <div>
          <div class="record-title">{{ job.role }}</div>
          <div class="record-sub">{{ job.company }}</div>
        </div>
        <span class="record-badge">{{ job.status === 'active' ? '● active' : job.period }}</span>
      </div>
      <div class="record-body">
        <div class="field-row">
          <div class="field-label">period</div>
          <div class="field-value"><p>{{ job.period }}</p></div>
        </div>
        <div class="field-row">
          <div class="field-label">responsibilities</div>
          <div class="field-value">
            <ul>
              <li v-for="(p, j) in job.points" :key="j">{{ p }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
