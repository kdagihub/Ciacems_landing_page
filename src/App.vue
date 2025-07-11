<template>
  <div id="app">
    <!-- Header -->
    <header class="header">
      <div class="container">
        <div class="header-content">
          <div class="logo">
            <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect width="40" height="40" rx="8" fill="#FACC15"/>
              <path d="M20 12L28 20L20 28L12 20L20 12Z" fill="#0F172A"/>
            </svg>
            <span class="logo-text">CIACEMS</span>
          </div>
          <nav class="nav">
            <a href="#services" class="nav-link">Services</a>
            <a href="#about" class="nav-link">À propos</a>
            <a href="#contact" class="nav-link">Contact</a>
          </nav>
        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-title">L'ingénierie au service du digital africain</h1>
          <p class="hero-subtitle">
            Chez CIACEMS, nous concevons des solutions numériques modernes, puissantes et accessibles 
            pour transformer durablement les activités des entreprises et organisations africaines.
          </p>
          <div class="hero-cta">
            <a href="#contact" class="btn btn-primary">Découvrir nos services</a>
            <a href="https://wa.me/+2250749123456" class="btn btn-secondary">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.891 3.426"/>
              </svg>
              WhatsApp
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
      <div class="container">
        <div class="about-content">
          <h2 class="section-title">À propos de CIACEMS</h2>
          <p class="about-description">
            <strong>CIACEMS</strong> (Cabinet d'Ingénierie Avancée et de Conception d'Environnements Sécurisés) 
            est une agence technologique basée à Abidjan, spécialisée en développement logiciel, création de 
            plateformes web, et solutions SaaS adaptées aux besoins réels du marché africain.
          </p>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="container">
        <h2 class="section-title">Nos Services</h2>
        <div class="services-grid">
          <div class="service-card">
            <div class="service-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/>
                <circle cx="12" cy="12" r="4"/>
              </svg>
            </div>
            <h3 class="service-title">Solutions SaaS</h3>
            <p class="service-subtitle">En développement ou disponibles</p>
            <ul class="service-list">
              <li>Gestion de fermes avicoles</li>
              <li>Gestion de pressing</li>
              <li>Gestion de livraison de gaz domestique</li>
              <li>Gestion scolaire pour établissements privés</li>
              <li>Facturation simplifiée pour PME</li>
            </ul>
          </div>
          <div class="service-card">
            <div class="service-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
              </svg>
            </div>
            <h3 class="service-title">Services Personnalisés</h3>
            <p class="service-subtitle">Solutions sur mesure</p>
            <ul class="service-list">
              <li>Création de sites vitrines professionnels</li>
              <li>Développement de tableaux de bord métiers</li>
              <li>Intégration d'API & automatisation</li>
              <li>Outils de collecte ou traitement de données</li>
              <li>Maintenance et hébergement sécurisé</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us Section -->
    <section class="why-choose">
      <div class="container">
        <h2 class="section-title">Pourquoi nous choisir ?</h2>
        <div class="features-grid">
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>
              </svg>
            </div>
            <h3 class="feature-title">Technologies modernes</h3>
            <p class="feature-description">Python, Vue.js, Docker</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/>
                <path d="M2 12h20"/>
              </svg>
            </div>
            <h3 class="feature-title">Solutions pensées pour l'Afrique</h3>
            <p class="feature-description">Adaptées au contexte africain</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                <circle cx="12" cy="7" r="4"/>
              </svg>
            </div>
            <h3 class="feature-title">Accompagnement sur mesure</h3>
            <p class="feature-description">Écoute et adaptation</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                <path d="M2 17l10 5 10-5"/>
                <path d="M2 12l10 5 10-5"/>
              </svg>
            </div>
            <h3 class="feature-title">Produits simples et efficaces</h3>
            <p class="feature-description">Accessibles et performants</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
      <div class="container">
        <div class="contact-content">
          <h2 class="section-title">Un projet ? Discutons-en.</h2>
          <div class="contact-methods">
            <a href="https://wa.me/+2250749123456" class="contact-btn whatsapp">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.891 3.426"/>
              </svg>
              Contactez-nous sur WhatsApp
            </a>
            <a href="mailto:contact@ciacems.com" class="contact-btn email">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                <polyline points="22,6 12,13 2,6"/>
              </svg>
              contact@ciacems.com
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-info">
            <p>&copy; 2025 CIACEMS - Tous droits réservés</p>
          </div>
          <div class="footer-links">
            <a href="#" class="footer-link">Facebook</a>
            <a href="#" class="footer-link">LinkedIn</a>
            <a href="https://wa.me/+2250749123456" class="footer-link">WhatsApp Business</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
/* CSS Reset et variables */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary-dark: #0F172A;
  --primary-yellow: #FACC15;
  --white: #FFFFFF;
  --gray-light: #E5E7EB;
  --gray-medium: #6B7280;
  --gray-darker: #374151;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: var(--white);
  background-color: var(--primary-dark);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header */
.header {
  background: var(--primary-dark);
  border-bottom: 1px solid var(--gray-light);
  padding: 1rem 0;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--primary-yellow);
}

.nav {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: var(--white);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: var(--primary-yellow);
}

/* Hero Section */
.hero {
  padding: 8rem 0 4rem;
  text-align: center;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.hero-title {
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  color: var(--white);
}

.hero-subtitle {
  font-size: 1.25rem;
  margin-bottom: 3rem;
  color: var(--gray-light);
  line-height: 1.8;
}

.hero-cta {
  display: flex;
  gap: 1rem;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border: none;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  cursor: pointer;
}

.btn-primary {
  background: var(--primary-yellow);
  color: var(--primary-dark);
}

.btn-primary:hover {
  background: #EAB308;
  transform: translateY(-2px);
}

.btn-secondary {
  background: transparent;
  color: var(--white);
  border: 2px solid var(--primary-yellow);
}

.btn-secondary:hover {
  background: var(--primary-yellow);
  color: var(--primary-dark);
}

/* About Section */
.about {
  padding: 4rem 0;
  background: linear-gradient(135deg, var(--primary-dark) 0%, #1E293B 100%);
}

.about-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.section-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 2rem;
  color: var(--primary-yellow);
}

.about-description {
  font-size: 1.1rem;
  color: var(--gray-light);
  line-height: 1.8;
}

/* Services Section */
.services {
  padding: 4rem 0;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.service-card {
  background: #1E293B;
  padding: 2rem;
  border-radius: 12px;
  border: 1px solid var(--gray-light);
  transition: transform 0.3s ease;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-icon {
  width: 48px;
  height: 48px;
  background: var(--primary-yellow);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
}

.service-icon svg {
  color: var(--primary-dark);
}

.service-title {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: var(--white);
}

.service-subtitle {
  color: var(--primary-yellow);
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.service-list {
  list-style: none;
}

.service-list li {
  padding: 0.5rem 0;
  color: var(--gray-light);
  position: relative;
  padding-left: 1.5rem;
}

.service-list li:before {
  content: "▶";
  color: var(--primary-yellow);
  position: absolute;
  left: 0;
}

/* Why Choose Us Section */
.why-choose {
  padding: 4rem 0;
  background: linear-gradient(135deg, var(--primary-dark) 0%, #1E293B 100%);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.feature-item {
  text-align: center;
  padding: 2rem;
}

.feature-icon {
  width: 64px;
  height: 64px;
  background: var(--primary-yellow);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
}

.feature-icon svg {
  color: var(--primary-dark);
}

.feature-title {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: var(--white);
}

.feature-description {
  color: var(--gray-light);
}

/* Contact Section */
.contact {
  padding: 4rem 0;
  text-align: center;
}

.contact-content {
  max-width: 600px;
  margin: 0 auto;
}

.contact-methods {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.contact-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.contact-btn.whatsapp {
  background: #25D366;
  color: var(--white);
}

.contact-btn.whatsapp:hover {
  background: #128C7E;
  transform: translateY(-2px);
}

.contact-btn.email {
  background: var(--primary-yellow);
  color: var(--primary-dark);
}

.contact-btn.email:hover {
  background: #EAB308;
  transform: translateY(-2px);
}

/* Footer */
.footer {
  background: #1E293B;
  padding: 2rem 0;
  border-top: 1px solid var(--gray-light);
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-info {
  color: var(--gray-light);
}

.footer-links {
  display: flex;
  gap: 1rem;
}

.footer-link {
  color: var(--gray-light);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: var(--primary-yellow);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-subtitle {
    font-size: 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .features-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  
  .nav {
    display: none;
  }
  
  .hero-cta {
    flex-direction: column;
  }
  
  .contact-methods {
    flex-direction: column;
  }
  
  .footer-content {
    flex-direction: column;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 15px;
  }
  
  .hero {
    padding: 6rem 0 3rem;
  }
  
  .service-card {
    padding: 1.5rem;
  }
  
  .feature-item {
    padding: 1.5rem;
  }
}
</style>