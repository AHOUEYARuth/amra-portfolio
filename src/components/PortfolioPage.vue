<template>
  <div class="portfolio-container">
    <!-- Header Section with Name -->
    <header class="portfolio-header">
      <h1 class="name">{{ name }}</h1>
      <p class="title">{{ jobTitle }}</p>
    </header>

    <!-- Contact Information Section -->
    <section class="contact-section">
      <h2>Contact Information</h2>
      <div class="contact-grid">
        <div class="contact-item">
          <span class="contact-label">Email:</span>
          <a :href="'mailto:' + contact.email" class="contact-value">{{ contact.email }}</a>
        </div>
        <div class="contact-item">
          <span class="contact-label">Phone:</span>
          <span class="contact-value">{{ contact.phone }}</span>
        </div>
        <div class="contact-item">
          <span class="contact-label">Location:</span>
          <span class="contact-value">{{ contact.location }}</span>
        </div>
        <div class="contact-item">
          <span class="contact-label">LinkedIn:</span>
          <a :href="contact.linkedin" target="_blank" class="contact-value">{{ contact.linkedin }}</a>
        </div>
      </div>
    </section>

    <!-- Education Section -->
    <section class="education-section">
      <h2>Education</h2>
      <div class="education-list">
        <div v-for="edu in education" :key="edu.id" class="education-item">
          <div class="education-header">
            <h3 class="degree">{{ edu.degree }}</h3>
            <span class="year">{{ edu.year }}</span>
          </div>
          <p class="institution">{{ edu.institution }}</p>
          <p class="location">{{ edu.location }}</p>
          <p v-if="edu.gpa" class="gpa">GPA: {{ edu.gpa }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'PortfolioPage',
  data() {
    return {
      name: 'Ruth Alida',
      jobTitle: 'Software Engineer',
      contact: {
        email: 'ruahoueya@gmail.com',
        phone: '+229 01 51 08 74 08',
        location: 'cotonou, Benin',
        linkedin: 'https://linkedin.com/in/ruth'
      },
      education: [
        {
          id: 1,
          degree: 'Bachelor of Science in Computer Science',
          institution: 'University of Technology',
          location: 'New York, NY',
          year: '2020-2024',
          gpa: '3.8/4.0'
        },
        {
          id: 2,
          degree: 'High School Diploma',
          institution: 'Central High School',
          location: 'Brooklyn, NY',
          year: '2016-2020',
          gpa: '3.9/4.0'
        }
      ]
    }
  }
}
</script>

<style scoped>
.portfolio-container {
  width: 100%;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Arial', sans-serif;
  line-height: 1.6;
  color: #333;
}

.portfolio-header {
  text-align: center;
  margin-bottom: 40px;
  padding: 30px 0;
  border-bottom: 3px solid #007bff;
}

.name {
  font-size: 2.5em;
  margin: 0;
  color: #2c3e50;
  font-weight: bold;
}

.title {
  font-size: 1.2em;
  color: #7f8c8d;
  margin: 10px 0 0 0;
  font-style: italic;
}

.contact-section, .education-section {
  margin-bottom: 40px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.contact-section h2, .education-section h2 {
  color: #2c3e50;
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid #007bff;
  font-size: 1.5em;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 15px;
}

.contact-item {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.contact-label {
  font-weight: bold;
  color: #495057;
  font-size: 0.9em;
}

.contact-value {
  color: #007bff;
  text-decoration: none;
  font-size: 1em;
}

.contact-value:hover {
  text-decoration: underline;
}

.education-list {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.education-item {
  padding: 20px;
  background: white;
  border-radius: 6px;
  border-left: 4px solid #007bff;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
}

.education-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 10px;
  flex-wrap: wrap;
  gap: 10px;
}

.degree {
  color: #2c3e50;
  margin: 0;
  font-size: 1.2em;
  flex: 1;
}

.year {
  color: #6c757d;
  font-weight: bold;
  background: #e9ecef;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 0.9em;
}

.institution {
  color: #495057;
  margin: 5px 0;
  font-weight: 500;
  font-size: 1.1em;
}

.location {
  color: #6c757d;
  margin: 5px 0;
  font-style: italic;
}

.gpa {
  color: #28a745;
  margin: 5px 0;
  font-weight: bold;
  font-size: 0.9em;
}

/* Responsive Design */
@media (max-width: 768px) {
  .portfolio-container {
    padding: 15px;
  }
  
  .name {
    font-size: 2em;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
  }
  
  .education-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .year {
    align-self: flex-start;
  }
}
</style>