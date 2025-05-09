// ExperienceSection.vue
<template>
  <div id="experience" class="experience-container">
    <div class="experience-header">
      <h2>Experience</h2>
    </div>
    <p class="experience-summary">Here is a quick summary of my most recent experiences:</p>
    
    <div class="experience-list">
      <div v-for="(job, index) in experiences" :key="index" class="experience-card">
        <div class="experience-logo">
          <img :src="job.logo" :alt="job.company + ' logo'" />
        </div>
        <div class="experience-content">
          <div class="experience-title">{{ job.title }}</div>
          <ul class="experience-details">
            <li v-for="(detail, detailIndex) in job.details" :key="detailIndex">
              <span v-html="detail"></span>
            </li>
          </ul>
        </div>
        <div class="experience-period">{{ job.period }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

import barcodegateLogo from '../assets/BarcodeGate.png';
import htgLogo from '../assets/HTG.png';
import damLogo from '../assets/Damascus_University.png';
import SmartWorkLogo from '../assets/SmartWorks.jpeg';

// Define the experiences data
const experiences = ref([
  {
    company: 'HTG - Honest Tech Guys',
    logo: htgLogo,
    title: 'Senior Software Engineer',
    period: 'Jul 2023 – Present',
    duration: '1 year (ongoing)',
    details: [
      'Built internal <strong>Laravel/.Net</strong> based API Gateway with service grouping and custom validators.',
      'Designed and deployed modular API systems for Malaysian F&B and logistics brands.',
      'Integrated third-party services such as eGHL, RazerPay, GrabExpress, and Xilnex.',
      'Deployed scalable containerized applications on AWS (EC2, RDS) using Docker.',
      'Mentored junior developers and participated in architectural planning.'
    ]
  },
  {
    company: 'SmartWork',
    logo: SmartWorkLogo,
    title: 'Backend Developer',
    period: 'Feb 2023 – Jan 2024',
    duration: '1 year',
    details: [
      'Developed <strong>Laravel/.Net</strong> backend services for many websites applications.',
      'Collaborated with frontend teams to ensure real-time sync and performance.',
      'Managed database optimization and API versioning.',
      'Worked on Maltepe Hospital website project.'
    ]
  },
  {
    company: 'BarcodeGate',
    logo: barcodegateLogo,
    title: 'Software & Hardware Developer',
    period: 'Jun 2016 – Sep 2022',
    duration: '6 years 4 months',
    details: [
      'Promoted from IT Technician to Full-Stack Developer using .NET and C#.',
      'Developed Laravel-based ticketing system for automating hardware support.',
      'Integrated .NET-based solutions for hardware-software automation workflows.'
    ]
  },
  {
    company: 'Damascus University',
    logo: damLogo,
    title: 'C++ and Java Instructor',
    period: 'May 2021 – Oct 2022',
    duration: '1 year 4 months',
    details: [
      'Taught object-oriented programming using C++ and Java Swing.',
      'Created a student innovation circle focused on real-world projects.',
      'Mentored student teams on projects like a console game and business apps.'
    ]
  }
]);


</script>

<style scoped>
.experience-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 1rem;
  color: #fff;
  font-family: sans-serif;
}

.experience-header {
  display: flex;
  justify-content: center;
  margin-bottom: 1rem;
}

.experience-header h2 {
  font-size: 1.25rem;
  font-weight: 500;
  background-color: rgba(255, 255, 255, 0.1);
  padding: 0.5rem 1.5rem;
  border-radius: 1.5rem;
}

.experience-summary {
  text-align: center;
  margin-bottom: 2rem;
  font-size: 1.25rem;
}

.experience-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.experience-card {
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 1.5rem;
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 0.5rem;
  padding: 1.5rem;
  align-items: start;
}

.experience-logo img {
  width: 120px;
  height: auto;
}

.experience-title {
  font-size: 1.25rem;
  font-weight: 500;
  margin-bottom: 1rem;
}

.experience-details {
  list-style-type: disc;
  padding-left: 1.5rem;
  margin: 0;
}

.experience-details li {
  margin-bottom: 0.75rem;
}

.experience-period {
  color: #ccc;
  white-space: nowrap;
}

@media (max-width: 768px) {
  .experience-card {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .experience-logo {
    text-align: center;
  }
  
  .experience-period {
    text-align: center;
  }
}
</style>