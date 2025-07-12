<template>
  <div id="app">
    <!-- Header -->
    <header class="header">
      <div class="container">
        <div class="header-content">
          <div class="logo">
            <img src="/logo_light.png" alt="CIACEMS Technologies" width="60" height="60" />
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
          <h1 class="hero-title">Votre site web livré en 1 semaine</h1>
          <p class="hero-subtitle">
            Nous digitalisons rapidement les activités des entreprises africaines. 
            Chez CIACEMS, obtenez votre première version fonctionnelle en seulement 7 jours, 
            avec des tarifs abordables et un accompagnement transparent.
          </p>
          <div class="hero-cta">
            <a href="#contact" class="btn btn-primary">Démarrer mon projet</a>
            <a href="https://wa.me/+2250749123456" class="btn btn-secondary">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.891 3.426"/>
              </svg>
              Consultation gratuite
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
      <div class="container">
        <div class="about-content">
          <h2 class="section-title">Notre Mission</h2>
          <p class="about-description">
            <strong>CIACEMS TECHNOLOGIES</strong> accélère la digitalisation des entreprises africaines. 
            Notre objectif : permettre à chaque entrepreneur et structure d'accéder à des outils digitaux 
            puissants et efficaces, quel que soit leur budget. Nous croyons en une Afrique connectée et compétitive.
          </p>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio">
      <div class="container">
        <h2 class="section-title">Nos Réalisations</h2>
        <p class="portfolio-subtitle">Découvrez comment nous avons transformé la présence digitale de nos clients</p>
        <div class="portfolio-grid">
          <div class="portfolio-item">
            <div class="portfolio-image">
              <div class="portfolio-placeholder">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <rect x="2" y="3" width="20" height="14" rx="2" ry="2"/>
                  <line x1="8" y1="21" x2="16" y2="21"/>
                  <line x1="12" y1="17" x2="12" y2="21"/>
                </svg>
              </div>
            </div>
            <div class="portfolio-content">
              <h3>Site E-commerce Moderne</h3>
              <p>Boutique en ligne avec paiement mobile intégré pour une PME ivoirienne</p>
              <span class="portfolio-tag">E-commerce</span>
            </div>
          </div>
          <div class="portfolio-item">
            <div class="portfolio-image">
              <div class="portfolio-placeholder">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/>
                  <polyline points="14,2 14,8 20,8"/>
                  <line x1="16" y1="13" x2="8" y2="13"/>
                  <line x1="16" y1="17" x2="8" y2="17"/>
                  <polyline points="10,9 9,9 8,9"/>
                </svg>
              </div>
            </div>
            <div class="portfolio-content">
              <h3>Système de Gestion Scolaire</h3>
              <p>Solution complète pour gérer élèves, notes et paiements d'un établissement privé</p>
              <span class="portfolio-tag">SaaS Éducation</span>
            </div>
          </div>
          <div class="portfolio-item">
            <div class="portfolio-image">
              <div class="portfolio-placeholder">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <circle cx="12" cy="12" r="3"/>
                  <path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1 1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"/>
                </svg>
              </div>
            </div>
            <div class="portfolio-content">
              <h3>Plateforme CRM Avancée</h3>
              <p>Outil de gestion client et suivi commercial pour une entreprise de services</p>
              <span class="portfolio-tag">CRM</span>
            </div>
          </div>
          <div class="portfolio-item">
            <div class="portfolio-image">
              <div class="portfolio-placeholder">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
                </svg>
              </div>
            </div>
            <div class="portfolio-content">
              <h3>Landing Page Conversion</h3>
              <p>Page de destination optimisée ayant généré +300% de leads pour un client</p>
              <span class="portfolio-tag">Landing Page</span>
            </div>
          </div>
        </div>
        <div class="portfolio-cta">
          <a href="#contact" class="btn btn-primary">Voir plus de réalisations</a>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="container">
        <h2 class="section-title">Révolutionnez votre présence digitale</h2>
        <p class="services-subtitle">
          Nous transformons votre vision en réalité numérique. Chaque solution est pensée pour booster votre activité et vous démarquer de la concurrence.
        </p>
        <div class="services-categories">
          <div class="service-category">
            <div class="category-header">
              <div class="category-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <rect x="2" y="3" width="20" height="14" rx="2" ry="2"/>
                  <line x1="8" y1="21" x2="16" y2="21"/>
                  <line x1="12" y1="17" x2="12" y2="21"/>
                </svg>
              </div>
              <h3 class="category-title">Sites Web & E-commerce</h3>
              <p class="category-subtitle">Votre vitrine digitale qui convertit 24h/24</p>
            </div>
            <ul class="category-services">
              <li>Sites vitrines professionnels</li>
              <li>Landing pages haute conversion</li>
              <li>Blogs et sites de contenu</li>
              <li>Boutiques e-commerce complètes</li>
              <li>Portails web avancés</li>
            </ul>
          </div>
          
          <div class="service-category">
            <div class="category-header">
              <div class="category-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/>
                  <circle cx="12" cy="12" r="4"/>
                </svg>
              </div>
              <h3 class="category-title">Solutions Métiers</h3>
              <p class="category-subtitle">Automatisez et optimisez vos processus</p>
            </div>
            <ul class="category-services">
              <li>Systèmes CRM personnalisés</li>
              <li>Solutions ERP sectorielles</li>
              <li>Gestion scolaire & éducative</li>
              <li>Outils de facturation</li>
              <li>Dashboards analytics</li>
            </ul>
          </div>
          
          <div class="service-category">
            <div class="category-header">
              <div class="category-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
                </svg>
              </div>
              <h3 class="category-title">Intégrations & Automatisation</h3>
              <p class="category-subtitle">Connectez et automatisez vos outils</p>
            </div>
            <ul class="category-services">
              <li>Intégrations API tierces</li>
              <li>Automatisation de processus</li>
              <li>Formations personnalisées</li>
              <li>Maintenance & support</li>
              <li>Consulting digital</li>
            </ul>
          </div>
        </div>
        
        <div class="services-cta">
          <div class="cta-content">
            <h3>Prêt à transformer votre activité ?</h3>
            <p>Discutons de votre projet et découvrons ensemble comment révolutionner votre présence digitale.</p>
            <a href="#contact" class="btn btn-primary">Démarrer ma transformation</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us Section -->
    <section class="why-choose">
      <div class="container">
        <h2 class="section-title">Nos Valeurs Ajoutées</h2>
        <div class="features-grid">
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>
              </svg>
            </div>
            <h3 class="feature-title">Rapidité de livraison</h3>
            <p class="feature-description">7 jours pour votre première version</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
              </svg>
            </div>
            <h3 class="feature-title">Disponibilité totale</h3>
            <p class="feature-description">Support réactif et accompagnement continu</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/>
                <circle cx="12" cy="12" r="3"/>
              </svg>
            </div>
            <h3 class="feature-title">Transparence absolue</h3>
            <p class="feature-description">Suivi en temps réel de votre projet</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                <path d="M2 17l10 5 10-5"/>
                <path d="M2 12l10 5 10-5"/>
              </svg>
            </div>
            <h3 class="feature-title">Tarifs abordables</h3>
            <p class="feature-description">Solutions adaptées à tous les budgets</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
      <div class="container">
        <div class="contact-content">
          <h2 class="section-title">Commençons votre projet digital</h2>
          <p class="hero-subtitle">
            Consultation gratuite • Devis sous 24h • Première version en 7 jours
          </p>
          <div class="contact-methods">
            <a href="https://wa.me/+2250749123456" class="contact-btn whatsapp">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.891 3.426"/>
              </svg>
              Consultation WhatsApp
            </a>
            <a href="mailto:contact@ciacems.com" class="contact-btn email">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                <polyline points="22,6 12,13 2,6"/>
              </svg>
              Demande de devis
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
  --primary-dark: #0F0F0F;
  --primary-blue: #00B4D8;
  --primary-gold: #F59E0B;
  --white: #FFFFFF;
  --gray-light: #F8FAFC;
  --gray-medium: #64748B;
  --gray-darker: #334155;
  --accent-blue: #0077B6;
  --accent-gold: #D97706;
  --text-dark: #0F172A;
  --text-light: #475569;
  --border-light: #E2E8F0;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: var(--text-dark);
  background-color: var(--white);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header */
.header {
  background: rgba(255, 255, 255, 0.95);
  border-bottom: 1px solid var(--border-light);
  padding: 1rem 0;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

.logo:hover {
  transform: scale(1.1);
}

.logo img {
  transition: all 0.3s ease;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
}

.nav {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: var(--text-dark);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: var(--primary-blue);
}

/* Hero Section */
.hero {
  padding: 8rem 0 4rem;
  text-align: center;
  background: linear-gradient(135deg, var(--gray-light) 0%, var(--white) 50%, var(--gray-light) 100%);
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 30%, rgba(0, 180, 216, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(245, 158, 11, 0.1) 0%, transparent 50%),
    linear-gradient(45deg, transparent 45%, rgba(0, 180, 216, 0.03) 50%, transparent 55%),
    linear-gradient(-45deg, transparent 45%, rgba(245, 158, 11, 0.03) 50%, transparent 55%);
  pointer-events: none;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}

.hero-title {
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  color: var(--text-dark);
}

.hero-subtitle {
  font-size: 1.25rem;
  margin-bottom: 3rem;
  color: var(--text-light);
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
  background: var(--primary-blue);
  color: var(--white);
}

.btn-primary:hover {
  background: var(--accent-blue);
  transform: translateY(-2px);
}

.btn-secondary {
  background: transparent;
  color: var(--primary-blue);
  border: 2px solid var(--primary-blue);
}

.btn-secondary:hover {
  background: var(--primary-blue);
  color: var(--white);
}

/* About Section */
.about {
  padding: 4rem 0;
  background: var(--gray-light);
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
  color: var(--text-dark);
}

.about-description {
  font-size: 1.1rem;
  color: var(--text-light);
  line-height: 1.8;
}

/* Portfolio Section */
.portfolio {
  padding: 4rem 0;
  background: var(--gray-light);
}

.portfolio-subtitle {
  text-align: center;
  font-size: 1.1rem;
  color: var(--text-light);
  margin-bottom: 3rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.portfolio-item {
  background: var(--white);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.portfolio-item:hover {
  transform: translateY(-8px);
  box-shadow: 0 8px 25px rgba(0, 180, 216, 0.15);
}

.portfolio-image {
  height: 200px;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--accent-blue) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.portfolio-placeholder {
  color: var(--white);
  opacity: 0.8;
}

.portfolio-content {
  padding: 1.5rem;
}

.portfolio-content h3 {
  font-size: 1.2rem;
  font-weight: bold;
  color: var(--text-dark);
  margin-bottom: 0.5rem;
}

.portfolio-content p {
  color: var(--text-light);
  font-size: 0.9rem;
  line-height: 1.5;
  margin-bottom: 1rem;
}

.portfolio-tag {
  display: inline-block;
  background: var(--primary-gold);
  color: var(--white);
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
}

.portfolio-cta {
  text-align: center;
}

/* Services Section */
.services {
  padding: 4rem 0;
}

.services-subtitle {
  text-align: center;
  font-size: 1.1rem;
  color: var(--text-light);
  margin-bottom: 3rem;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.services-categories {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.service-category {
  background: var(--white);
  border-radius: 16px;
  padding: 2rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  border: 1px solid var(--border-light);
}

.service-category:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 30px rgba(0, 180, 216, 0.15);
  border-color: var(--primary-blue);
}

.category-header {
  text-align: center;
  margin-bottom: 1.5rem;
}

.category-icon {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--accent-blue) 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  color: var(--white);
}

.category-title {
  font-size: 1.4rem;
  font-weight: bold;
  color: var(--text-dark);
  margin-bottom: 0.5rem;
}

.category-subtitle {
  font-size: 0.95rem;
  color: var(--text-light);
  line-height: 1.4;
}

.category-services {
  list-style: none;
  padding: 0;
}

.category-services li {
  padding: 0.75rem 0;
  color: var(--text-light);
  position: relative;
  padding-left: 1.5rem;
  border-bottom: 1px solid var(--border-light);
}

.category-services li:last-child {
  border-bottom: none;
}

.category-services li:before {
  content: "✓";
  color: var(--primary-gold);
  font-weight: bold;
  position: absolute;
  left: 0;
}

.services-cta {
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--accent-blue) 100%);
  border-radius: 20px;
  padding: 3rem 2rem;
  text-align: center;
  color: var(--white);
  margin-top: 3rem;
}

.cta-content h3 {
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.cta-content p {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.cta-content .btn {
  background: var(--primary-gold);
  color: var(--white);
  border: 2px solid var(--primary-gold);
}

.cta-content .btn:hover {
  background: var(--white);
  color: var(--primary-blue);
}



/* Why Choose Us Section */
.why-choose {
  padding: 4rem 0;
  background: var(--white);
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
  background: var(--primary-gold);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
}

.feature-icon svg {
  color: var(--white);
}

.feature-title {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: var(--text-dark);
}

.feature-description {
  color: var(--text-light);
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
  background: var(--primary-gold);
  color: var(--white);
}

.contact-btn.email:hover {
  background: var(--accent-gold);
  transform: translateY(-2px);
}

/* Footer */
.footer {
  background: var(--gray-light);
  padding: 2rem 0;
  border-top: 1px solid var(--border-light);
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-info {
  color: var(--text-light);
}

.footer-links {
  display: flex;
  gap: 1rem;
}

.footer-link {
  color: var(--text-light);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: var(--primary-blue);
}

/* Responsive Design */
@media (max-width: 1024px) {
  .features-grid {
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  }
  
  .portfolio-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
  }
  
  .services-categories {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 6rem 0 3rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
    line-height: 1.2;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .features-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1.5rem;
  }
  
  .nav {
    display: none;
  }
  
  .logo img {
    width: 50px;
    height: 50px;
  }
  
  .hero-cta {
    flex-direction: column;
    gap: 1rem;
  }
  
  .contact-methods {
    flex-direction: column;
  }
  
  .footer-content {
    flex-direction: column;
    text-align: center;
    gap: 1.5rem;
  }
  
  .header-content {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 15px;
  }
  
  .hero {
    padding: 5rem 0 2rem;
  }
  
  .hero-title {
    font-size: 2rem;
    line-height: 1.1;
  }
  
  .hero-subtitle {
    font-size: 1rem;
    margin-bottom: 2rem;
  }
  
  .section-title {
    font-size: 1.75rem;
  }
  
  .feature-item {
    padding: 1.5rem;
  }
  
  .btn {
    padding: 0.875rem 1.5rem;
    font-size: 0.9rem;
  }
  
  .logo img {
    width: 45px;
    height: 45px;
  }
  
  .about, .services, .why-choose, .contact, .portfolio {
    padding: 3rem 0;
  }
  
  .portfolio-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .portfolio-image {
    height: 150px;
  }
  
  .services-cta {
    padding: 2rem 1rem;
  }
  
  .cta-content h3 {
    font-size: 1.5rem;
  }
  
  .category-icon {
    width: 60px;
    height: 60px;
  }
}
</style>