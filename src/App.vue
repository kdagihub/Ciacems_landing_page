<template>
  <div id="app" class="min-h-screen bg-gradient-to-br from-slate-50 to-blue-50">
    <!-- Header -->
    <header class="header">
      <div class="container">
        <div class="header-content">
          <div class="logo">
            <img src="/logo_light.png" alt="CIACEMS Technologies" class="logo-img" />
            <span class="logo-text">CIACEMS</span>
          </div>
          <nav class="nav">
            <a href="#services" class="nav-link">Services</a>
            <a href="#portfolio" class="nav-link">Portfolio</a>
            <a href="#about" class="nav-link">À propos</a>
            <button class="btn btn-primary">Devis gratuit</button>
          </nav>
        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <div class="hero-badge">
            🚀 Cabinet d'ingénierie informatique et agence Web premium
          </div>
          <h1 class="hero-title">Créons ensemble votre
            présence digitale</h1>
          <p class="hero-subtitle">
            Nous digitalisons rapidement les activités des entreprises africaines. 
            Chez CIACEMS, obtenez votre première version fonctionnelle en seulement 7 jours, 
            avec des tarifs abordables et un accompagnement transparent.
          </p>
          <div class="hero-cta">
            <button class="btn btn-primary btn-lg">
              Voir nos réalisations
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="ml-2">
                <line x1="5" y1="12" x2="19" y2="12"/>
                <polyline points="12,5 19,12 12,19"/>
              </svg>
            </button>
            <button class="btn btn-secondary btn-lg">Consultation gratuite</button>
          </div>
          <div class="hero-stats">
            <div class="stat-item">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26"/>
              </svg>
              <span>4.9/5 sur Google</span>
            </div>
            <div class="stat-item">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
                <circle cx="9" cy="7" r="4"/>
                <path d="m22 21-3-3m0 0a2 2 0 0 0-3-3m3 3a2 2 0 0 1-3 3"/>
              </svg>
              <span>200+ clients satisfaits</span>
            </div>
            <div class="stat-item">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M9 12l2 2 4-4"/>
                <circle cx="12" cy="12" r="10"/>
              </svg>
              <span>100% sur-mesure</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="portfolio">
      <div class="container">
        <div class="portfolio-header">
          <h2 class="section-title">Quelques réalisations
          </h2>
          <p class="portfolio-subtitle">
            Découvrez nos créations digitales qui transforment les entreprises africaines
          </p>
        </div>
      </div>

      <div class="portfolio-container-full">
        <div class="portfolio-scroll">
            <div v-for="(project, index) in portfolioProjects" :key="index" 
                 class="portfolio-card" 
                 @click="openProject(project)">
              <div class="portfolio-image">
                <img :src="project.image" :alt="project.title" />
                <div class="portfolio-overlay">
                  <div class="portfolio-content">
                    <h3 class="portfolio-title">{{ project.title }}</h3>
                    <p class="portfolio-description">{{ project.description }}</p>
                    <div class="portfolio-tags">
                      <span v-for="tag in project.tags" :key="tag" class="portfolio-tag">
                        {{ tag }}
                      </span>
                    </div>
                    <div class="portfolio-cta">
                      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/>
                        <polyline points="15,3 21,3 21,9"/>
                        <line x1="10" y1="14" x2="21" y2="3"/>
                      </svg>
                      <span>Voir le projet</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
        </div>
      </div>

      <div class="container">
        <div class="portfolio-stats">
          <div class="stat-box">
            <div class="stat-number">{{ portfolioProjects.length }}+</div>
            <div class="stat-label">Projets Livrés</div>
          </div>
          <div class="stat-box">
            <div class="stat-number">100%</div>
            <div class="stat-label">Clients Satisfaits</div>
          </div>
          <div class="stat-box">
            <div class="stat-number">7 jours</div>
            <div class="stat-label">Délai Moyen</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Values Section -->
    <section class="values">
      <div class="container">
        <div class="values-content">
          <div class="values-text">
            <h2 class="values-title">Ce qui nous rend différents</h2>
            <p class="values-subtitle">
              Nous révolutionnons la digitalisation en Afrique avec des valeurs fortes et une approche moderne
            </p>
          </div>
          <div class="values-grid">
            <div v-for="(value, index) in companyValues" :key="index" class="value-card">
              <div class="value-icon" :class="value.iconColor">
                <!-- Rapidité Icon -->
                <svg v-if="value.icon === 'Speed'" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <circle cx="12" cy="12" r="10"/>
                  <polyline points="12,6 12,12 16,14"/>
                </svg>
                
                <!-- Transparence Icon -->
                <svg v-else-if="value.icon === 'Transparency'" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/>
                  <circle cx="12" cy="12" r="3"/>
                </svg>
                
                <!-- Technologie Icon -->
                <svg v-else-if="value.icon === 'Technology'" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <rect x="2" y="3" width="20" height="14" rx="2" ry="2"/>
                  <line x1="8" y1="21" x2="16" y2="21"/>
                  <line x1="12" y1="17" x2="12" y2="21"/>
                </svg>
                
                <!-- Prix Icon -->
                <svg v-else-if="value.icon === 'Price'" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <line x1="12" y1="1" x2="12" y2="23"/>
                  <path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/>
                </svg>
              </div>
              <h3 class="value-title">{{ value.title }}</h3>
              <p class="value-description">{{ value.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="container">
        <div class="services-header">
          <h2 class="section-title">Nos Expertises Web</h2>
          <p class="services-subtitle">
            Chaque projet est unique. Découvrez nos solutions adaptées à vos besoins spécifiques.
          </p>
        </div>

        <div class="services-grid">
          <div v-for="(service, index) in websiteTypes" :key="index" class="service-card">
            <div class="service-mockup">
              <!-- Site Vitrine Mockup -->
              <svg v-if="service.mockup === 'VitrineMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="40" fill="#1e293b" />
                <rect x="20" y="15" width="60" height="10" fill="#00B4D8" rx="2" />
                <rect x="220" y="12" width="15" height="6" fill="#64748b" rx="1" />
                <rect x="240" y="12" width="15" height="6" fill="#64748b" rx="1" />
                <rect x="260" y="12" width="15" height="6" fill="#64748b" rx="1" />
                <rect x="50" y="60" width="200" height="8" fill="#1e293b" rx="2" />
                <rect x="80" y="75" width="140" height="4" fill="#64748b" rx="1" />
                <rect x="90" y="85" width="120" height="4" fill="#64748b" rx="1" />
                <rect x="125" y="100" width="50" height="20" fill="#00B4D8" rx="4" />
                <rect x="30" y="140" width="80" height="40" fill="#e2e8f0" rx="4" />
                <rect x="120" y="140" width="80" height="40" fill="#e2e8f0" rx="4" />
                <rect x="210" y="140" width="80" height="40" fill="#e2e8f0" rx="4" />
              </svg>
              
              <!-- E-commerce Mockup -->
              <svg v-else-if="service.mockup === 'EcommerceMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="35" fill="#1e293b" />
                <rect x="20" y="12" width="50" height="8" fill="#00B4D8" rx="2" />
                <circle cx="260" cy="17" r="8" fill="#F59E0B" />
                <text x="260" y="21" text-anchor="middle" font-size="8" fill="white">3</text>
                <rect x="20" y="50" width="80" height="60" fill="#e2e8f0" rx="4" />
                <rect x="25" y="55" width="70" height="35" fill="#f1f5f9" rx="2" />
                <rect x="25" y="95" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="25" y="102" width="25" height="4" fill="#F59E0B" rx="1" />
                <rect x="110" y="50" width="80" height="60" fill="#e2e8f0" rx="4" />
                <rect x="115" y="55" width="70" height="35" fill="#f1f5f9" rx="2" />
                <rect x="115" y="95" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="115" y="102" width="25" height="4" fill="#F59E0B" rx="1" />
                <rect x="200" y="50" width="80" height="60" fill="#e2e8f0" rx="4" />
                <rect x="205" y="55" width="70" height="35" fill="#f1f5f9" rx="2" />
                <rect x="205" y="95" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="205" y="102" width="25" height="4" fill="#F59E0B" rx="1" />
                <rect x="20" y="120" width="80" height="60" fill="#e2e8f0" rx="4" />
                <rect x="110" y="120" width="80" height="60" fill="#e2e8f0" rx="4" />
                <rect x="200" y="120" width="80" height="60" fill="#e2e8f0" rx="4" />
              </svg>
              
              <!-- Blog Mockup -->
              <svg v-else-if="service.mockup === 'BlogMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="30" fill="#1e293b" />
                <rect x="20" y="10" width="80" height="8" fill="#00B4D8" rx="2" />
                <rect x="20" y="45" width="180" height="8" fill="#1e293b" rx="2" />
                <rect x="20" y="58" width="160" height="4" fill="#64748b" rx="1" />
                <rect x="20" y="66" width="170" height="4" fill="#64748b" rx="1" />
                <rect x="20" y="74" width="150" height="4" fill="#64748b" rx="1" />
                <rect x="20" y="85" width="180" height="60" fill="#e2e8f0" rx="4" />
                <rect x="20" y="150" width="100" height="4" fill="#64748b" rx="1" />
                <rect x="20" y="158" width="80" height="4" fill="#64748b" rx="1" />
                <rect x="220" y="45" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="220" y="58" width="60" height="20" fill="#e2e8f0" rx="2" />
                <rect x="220" y="85" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="220" y="98" width="60" height="4" fill="#64748b" rx="1" />
                <rect x="220" y="106" width="50" height="4" fill="#64748b" rx="1" />
                <rect x="220" y="114" width="55" height="4" fill="#64748b" rx="1" />
              </svg>
              
              <!-- Landing Page Mockup -->
              <svg v-else-if="service.mockup === 'LandingMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="25" fill="#1e293b" />
                <rect x="20" y="8" width="40" height="6" fill="#00B4D8" rx="1" />
                <rect x="250" y="6" width="30" height="10" fill="#F59E0B" rx="2" />
                <rect x="75" y="50" width="150" height="10" fill="#1e293b" rx="2" />
                <rect x="100" y="68" width="100" height="4" fill="#64748b" rx="1" />
                <rect x="110" y="78" width="80" height="4" fill="#64748b" rx="1" />
                <rect x="125" y="95" width="50" height="20" fill="#F59E0B" rx="4" />
                <circle cx="80" cy="140" r="15" fill="#00B4D8" />
                <rect x="105" y="135" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="105" y="143" width="60" height="3" fill="#64748b" rx="1" />
                <circle cx="80" cy="170" r="15" fill="#00B4D8" />
                <rect x="105" y="165" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="105" y="173" width="60" height="3" fill="#64748b" rx="1" />
                <circle cx="200" cy="140" r="15" fill="#00B4D8" />
                <rect x="225" y="135" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="225" y="143" width="50" height="3" fill="#64748b" rx="1" />
              </svg>
              
              <!-- Event Mockup -->
              <svg v-else-if="service.mockup === 'EventMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="30" fill="#00B4D8" />
                <rect x="20" y="10" width="60" height="8" fill="white" rx="2" />
                <rect x="250" y="8" width="30" height="10" fill="#0077B6" rx="2" />
                <rect x="20" y="45" width="80" height="40" fill="#00B4D8" rx="4" />
                <text x="60" y="60" text-anchor="middle" font-size="12" fill="white" font-weight="bold">15</text>
                <text x="60" y="75" text-anchor="middle" font-size="8" fill="white">MARS</text>
                <rect x="110" y="50" width="120" height="6" fill="#1e293b" rx="1" />
                <rect x="110" y="62" width="100" height="4" fill="#64748b" rx="1" />
                <rect x="110" y="70" width="80" height="4" fill="#64748b" rx="1" />
                <rect x="110" y="82" width="60" height="15" fill="#F59E0B" rx="3" />
                <rect x="20" y="110" width="260" height="4" fill="#1e293b" rx="1" />
                <rect x="20" y="125" width="80" height="20" fill="#e2e8f0" rx="2" />
                <rect x="110" y="125" width="80" height="20" fill="#e2e8f0" rx="2" />
                <rect x="200" y="125" width="80" height="20" fill="#e2e8f0" rx="2" />
                <circle cx="40" cy="170" r="12" fill="#64748b" />
                <circle cx="80" cy="170" r="12" fill="#64748b" />
                <circle cx="120" cy="170" r="12" fill="#64748b" />
              </svg>
              
              <!-- ERP Mockup -->
              <svg v-else-if="service.mockup === 'ERPMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="30" fill="#1e293b" />
                <rect x="10" y="8" width="20" height="12" fill="#00B4D8" rx="2" />
                <rect x="40" y="10" width="30" height="4" fill="#64748b" rx="1" />
                <rect x="80" y="10" width="30" height="4" fill="#64748b" rx="1" />
                <rect x="120" y="10" width="30" height="4" fill="#64748b" rx="1" />
                <rect x="0" y="30" width="60" height="170" fill="#f1f5f9" />
                <rect x="10" y="40" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="10" y="50" width="35" height="3" fill="#64748b" rx="1" />
                <rect x="10" y="58" width="35" height="3" fill="#64748b" rx="1" />
                <rect x="10" y="66" width="35" height="3" fill="#64748b" rx="1" />
                <rect x="10" y="80" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="10" y="90" width="35" height="3" fill="#64748b" rx="1" />
                <rect x="10" y="98" width="35" height="3" fill="#64748b" rx="1" />
                <rect x="70" y="40" width="220" height="30" fill="#e2e8f0" rx="4" />
                <rect x="80" y="50" width="60" height="8" fill="#1e293b" rx="2" />
                <rect x="80" y="60" width="40" height="4" fill="#00B4D8" rx="1" />
                <rect x="160" y="50" width="60" height="8" fill="#1e293b" rx="2" />
                <rect x="160" y="60" width="40" height="4" fill="#F59E0B" rx="1" />
                <rect x="70" y="80" width="100" height="60" fill="#e2e8f0" rx="4" />
                <rect x="180" y="80" width="110" height="60" fill="#e2e8f0" rx="4" />
                <rect x="70" y="150" width="220" height="40" fill="#f8fafc" stroke="#e2e8f0" />
                <rect x="70" y="150" width="220" height="8" fill="#f1f5f9" />
              </svg>
              
              <!-- CRM Mockup -->
              <svg v-else-if="service.mockup === 'CRMMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <rect x="0" y="0" width="300" height="30" fill="#1e293b" />
                <rect x="20" y="10" width="50" height="8" fill="#00B4D8" rx="2" />
                <circle cx="260" cy="15" r="8" fill="#64748b" />
                <rect x="20" y="45" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="20" y="60" width="60" height="80" fill="#f1f5f9" rx="4" />
                <rect x="25" y="70" width="50" height="15" fill="#F59E0B" rx="2" />
                <rect x="25" y="90" width="50" height="15" fill="#F59E0B" rx="2" />
                <rect x="25" y="110" width="50" height="15" fill="#F59E0B" rx="2" />
                <rect x="90" y="45" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="90" y="60" width="60" height="80" fill="#f1f5f9" rx="4" />
                <rect x="95" y="70" width="50" height="15" fill="#00B4D8" rx="2" />
                <rect x="95" y="90" width="50" height="15" fill="#00B4D8" rx="2" />
                <rect x="160" y="45" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="160" y="60" width="60" height="80" fill="#f1f5f9" rx="4" />
                <rect x="165" y="70" width="50" height="15" fill="#10b981" rx="2" />
                <rect x="230" y="45" width="60" height="6" fill="#1e293b" rx="1" />
                <rect x="230" y="60" width="60" height="80" fill="#f1f5f9" rx="4" />
                <rect x="235" y="70" width="50" height="15" fill="#ef4444" rx="2" />
                <rect x="235" y="90" width="50" height="15" fill="#ef4444" rx="2" />
                <rect x="20" y="155" width="260" height="35" fill="#e2e8f0" rx="4" />
                <rect x="30" y="165" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="30" y="173" width="25" height="6" fill="#10b981" rx="1" />
                <rect x="100" y="165" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="100" y="173" width="25" height="6" fill="#00B4D8" rx="1" />
                <rect x="170" y="165" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="170" y="173" width="25" height="6" fill="#F59E0B" rx="1" />
              </svg>
              
              <!-- Mobile App Mockup -->
              <svg v-else-if="service.mockup === 'MobileMockup'" viewBox="0 0 300 200" class="w-full h-full">
                <rect width="300" height="200" fill="#f8fafc" stroke="#e2e8f0" stroke-width="1" />
                <!-- iPhone mockup -->
                <rect x="80" y="20" width="70" height="120" fill="#1e293b" rx="12" />
                <rect x="85" y="30" width="60" height="100" fill="#f8fafc" rx="6" />
                <rect x="85" y="30" width="60" height="15" fill="#00B4D8" rx="6" />
                <circle cx="95" cy="37" r="2" fill="white" />
                <rect x="100" y="35" width="30" height="4" fill="white" rx="1" />
                <circle cx="135" cy="37" r="2" fill="white" />
                <rect x="90" y="55" width="50" height="6" fill="#1e293b" rx="1" />
                <rect x="90" y="68" width="25" height="20" fill="#00B4D8" rx="2" />
                <rect x="120" y="68" width="15" height="20" fill="#F59E0B" rx="2" />
                <rect x="90" y="95" width="50" height="4" fill="#64748b" rx="1" />
                <rect x="90" y="103" width="35" height="4" fill="#64748b" rx="1" />
                <rect x="90" y="115" width="50" height="10" fill="#10b981" rx="2" />
                
                <!-- Android mockup -->
                <rect x="170" y="20" width="70" height="120" fill="#34d399" rx="12" />
                <rect x="175" y="30" width="60" height="100" fill="#f8fafc" rx="6" />
                <rect x="175" y="30" width="60" height="15" fill="#00B4D8" rx="6" />
                <circle cx="185" cy="37" r="2" fill="white" />
                <rect x="190" y="35" width="30" height="4" fill="white" rx="1" />
                <circle cx="225" cy="37" r="2" fill="white" />
                <rect x="180" y="55" width="50" height="6" fill="#1e293b" rx="1" />
                <rect x="180" y="68" width="25" height="20" fill="#F59E0B" rx="2" />
                <rect x="210" y="68" width="15" height="20" fill="#00B4D8" rx="2" />
                <rect x="180" y="95" width="50" height="4" fill="#64748b" rx="1" />
                <rect x="180" y="103" width="35" height="4" fill="#64748b" rx="1" />
                <rect x="180" y="115" width="50" height="10" fill="#10b981" rx="2" />
                
                <!-- Features indicators -->
                <rect x="20" y="160" width="15" height="15" fill="#00B4D8" rx="2" />
                <rect x="42" y="164" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="42" y="170" width="25" height="3" fill="#64748b" rx="1" />
                
                <rect x="120" y="160" width="15" height="15" fill="#F59E0B" rx="2" />
                <rect x="142" y="164" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="142" y="170" width="30" height="3" fill="#64748b" rx="1" />
                
                <rect x="220" y="160" width="15" height="15" fill="#10b981" rx="2" />
                <rect x="242" y="164" width="40" height="4" fill="#1e293b" rx="1" />
                <rect x="242" y="170" width="35" height="3" fill="#64748b" rx="1" />
              </svg>
            </div>
            <div class="service-content">
              <div class="service-header">
                <div :class="['service-icon', service.color]">
                  <!-- Globe Icon -->
                  <svg v-if="service.icon === 'GlobeIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="2" y1="12" x2="22" y2="12"/>
                    <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/>
                  </svg>
                  
                  <!-- Shopping Cart Icon -->
                  <svg v-else-if="service.icon === 'ShoppingCartIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="9" cy="21" r="1"/>
                    <circle cx="20" cy="21" r="1"/>
                    <path d="m1 1 4 4 3.09 13.64A2 2 0 0 0 10 20h8.21a2 2 0 0 0 1.91-1.36L22 10H6"/>
                  </svg>
                  
                  <!-- File Text Icon -->
                  <svg v-else-if="service.icon === 'FileTextIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/>
                    <polyline points="14,2 14,8 20,8"/>
                    <line x1="16" y1="13" x2="8" y2="13"/>
                    <line x1="16" y1="17" x2="8" y2="17"/>
                    <polyline points="10,9 9,9 8,9"/>
                  </svg>
                  
                  <!-- Trending Up Icon -->
                  <svg v-else-if="service.icon === 'TrendingUpIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/>
                    <polyline points="17 6 23 6 23 12"/>
                  </svg>
                  
                  <!-- Calendar Icon -->
                  <svg v-else-if="service.icon === 'CalendarIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <rect x="3" y="4" width="18" height="18" rx="2" ry="2"/>
                    <line x1="16" y1="2" x2="16" y2="6"/>
                    <line x1="8" y1="2" x2="8" y2="6"/>
                    <line x1="3" y1="10" x2="21" y2="10"/>
                  </svg>
                  
                  <!-- Database Icon -->
                  <svg v-else-if="service.icon === 'DatabaseIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <ellipse cx="12" cy="5" rx="9" ry="3"/>
                    <path d="m3 5 0 14c0 1.4 4 3 9 3s9-1.6 9-3V5"/>
                    <path d="m3 12c0 1.4 4 3 9 3s9-1.6 9-3"/>
                  </svg>
                  
                  <!-- User Check Icon -->
                  <svg v-else-if="service.icon === 'UserCheckIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/>
                    <circle cx="9" cy="7" r="4"/>
                    <polyline points="16 11 18 13 22 9"/>
                  </svg>
                  
                  <!-- Smartphone Icon -->
                  <svg v-else-if="service.icon === 'SmartphoneIcon'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <rect x="5" y="2" width="14" height="20" rx="2" ry="2"/>
                    <line x1="12" y1="18" x2="12.01" y2="18"/>
                  </svg>
                </div>
                <h3 class="service-title">{{ service.title }}</h3>
              </div>
              <p class="service-description">{{ service.description }}</p>
              <ul class="service-features">
                <li v-for="(feature, idx) in service.features" :key="idx">
                  <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M9 12l2 2 4-4"/>
                    <circle cx="12" cy="12" r="10"/>
                  </svg>
                  {{ feature }}
                </li>
              </ul>
              <button class="btn btn-outline service-btn">En savoir plus</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us Section -->
    <section class="why-choose-us">
      <div class="container">
        <div class="why-content">
          <div class="why-header">
            <h2 class="section-title">Pourquoi Nous Choisir ?</h2>
            <p class="why-subtitle">
              Notre mission : démocratiser la digitalisation des entreprises africaines avec innovation et excellence
            </p>
          </div>
          
          <div class="why-grid">
            <div class="why-mission">
              <div class="mission-card">
                <div class="mission-icon">
                  <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                    <path d="M2 17l10 5 10-5"/>
                    <path d="M2 12l10 5 10-5"/>
                  </svg>
                </div>
                <h3 class="mission-title">Notre Vision</h3>
                <p class="mission-description">
                  Rendre accessible la digitalisation des activités et entreprises africaines et dans le monde, 
                  en utilisant les nouvelles technologies pour créer un impact positif et durable.
                </p>
              </div>
            </div>
            
            <div class="why-advantages">
              <div v-for="(advantage, index) in whyAdvantages" :key="index" class="advantage-item">
                <div class="advantage-icon">
                  <!-- Écoute Icon -->
                  <svg v-if="advantage.icon === 'Listen'" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M3 11h3l3-5 4 10 4-10 3 5h3"/>
                  </svg>
                  
                  <!-- Solutions Icon -->
                  <svg v-else-if="advantage.icon === 'Solutions'" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M9 12l2 2 4-4"/>
                    <path d="M21 12c-1.4 0-4.5-1.1-6-3-1.5 1.9-4.6 3-6 3s-4.5-1.1-6-3c-1.5 1.9-4.6 3-6 3"/>
                    <path d="M21 21c-1.4 0-4.5-1.1-6-3-1.5 1.9-4.6 3-6 3s-4.5-1.1-6-3c-1.5 1.9-4.6 3-6 3"/>
                    <path d="M21 3c-1.4 0-4.5-1.1-6-3-1.5 1.9-4.6 3-6 3s-4.5-1.1-6-3c-1.5 1.9-4.6 3-6 3"/>
                  </svg>
                  
                  <!-- Innovation Icon -->
                  <svg v-else-if="advantage.icon === 'Innovation'" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="5"/>
                    <line x1="12" y1="1" x2="12" y2="3"/>
                    <line x1="12" y1="21" x2="12" y2="23"/>
                    <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/>
                    <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
                    <line x1="1" y1="12" x2="3" y2="12"/>
                    <line x1="21" y1="12" x2="23" y2="12"/>
                    <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/>
                    <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
                  </svg>
                  
                  <!-- Engagement Icon -->
                  <svg v-else-if="advantage.icon === 'Engagement'" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
                  </svg>
                </div>
                <h4 class="advantage-title">{{ advantage.title }}</h4>
                <p class="advantage-description">{{ advantage.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="process">
      <div class="container">
        <div class="process-header">
          <h2 class="section-title">Notre Processus de Création</h2>
          <p class="process-subtitle">Une méthodologie éprouvée pour des résultats exceptionnels</p>
        </div>

        <div class="process-steps">
          <div v-for="(step, index) in processSteps" :key="index" class="process-step">
            <div class="step-number">{{ step.step }}</div>
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-description">{{ step.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2 class="cta-title">Prêt à transformer votre vision en réalité ?</h2>
          <p class="cta-subtitle">Obtenez un devis personnalisé en moins de 24h</p>
          <div class="cta-buttons">
            <button class="btn btn-secondary btn-lg">
              Devis gratuit
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="ml-2">
                <line x1="5" y1="12" x2="19" y2="12"/>
                <polyline points="12,5 19,12 12,19"/>
              </svg>
            </button>
            <button class="btn btn-outline-white btn-lg">Planifier un appel</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-grid">
          <div class="footer-brand">
            <div class="footer-logo">
              <img src="/logo_light.png" alt="CIACEMS Technologies" class="footer-logo-img" />
              <span class="footer-logo-text">CIACEMS</span>
            </div>
            <p class="footer-description">
              Votre partenaire digital pour des solutions web innovantes et performantes en Afrique.
            </p>
          </div>

          <div class="footer-column">
            <h4 class="footer-title">Services</h4>
            <ul class="footer-links">
              <li><a href="#" class="footer-link">Sites Vitrines</a></li>
              <li><a href="#" class="footer-link">E-commerce</a></li>
              <li><a href="#" class="footer-link">Applications Web</a></li>
              <li><a href="#" class="footer-link">Solutions SaaS</a></li>
            </ul>
          </div>

          <div class="footer-column">
            <h4 class="footer-title">Entreprise</h4>
            <ul class="footer-links">
              <li><a href="#" class="footer-link">À propos</a></li>
              <li><a href="#" class="footer-link">Portfolio</a></li>
              <li><a href="#" class="footer-link">Blog</a></li>
              <li><a href="#" class="footer-link">Contact</a></li>
            </ul>
          </div>

          <div class="footer-column">
            <h4 class="footer-title">Contact</h4>
            <ul class="footer-contact">
              <li>contact@ciacems.com</li>
              <li>+225 07 49 12 34 56</li>
              <li>Abidjan, Côte d'Ivoire</li>
            </ul>
          </div>
        </div>

        <div class="footer-bottom">
          <p>&copy; 2025 CIACEMS Technologies. Tous droits réservés.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      websiteTypes: [
        {
          title: "Site Vitrine",
          description: "Présentez votre entreprise avec élégance",
          features: ["Design responsive", "SEO optimisé", "Contact intégré"],
          icon: "GlobeIcon",
          mockup: "VitrineMockup",
          color: "bg-blue-500",
        },
        {
          title: "E-commerce",
          description: "Vendez en ligne avec une boutique performante",
          features: ["Paiement sécurisé", "Gestion stock", "Analytics"],
          icon: "ShoppingCartIcon",
          mockup: "EcommerceMockup",
          color: "bg-green-500",
        },
        {
          title: "Blog",
          description: "Partagez votre expertise et engagez votre audience",
          features: ["CMS intuitif", "Commentaires", "Newsletter"],
          icon: "FileTextIcon",
          mockup: "BlogMockup",
          color: "bg-purple-500",
        },
        {
          title: "Landing Page",
          description: "Convertissez vos visiteurs en clients",
          features: ["Taux conversion élevé", "A/B testing", "Formulaires"],
          icon: "TrendingUpIcon",
          mockup: "LandingMockup",
          color: "bg-orange-500",
        },
        {
          title: "Site Événementiel",
          description: "Organisez et promouvez vos événements",
          features: ["Billetterie", "Programme", "Speakers"],
          icon: "CalendarIcon",
          mockup: "EventMockup",
          color: "bg-pink-500",
        },
        {
          title: "ERP",
          description: "Gérez votre entreprise de A à Z",
          features: ["Gestion complète", "Reporting", "Multi-utilisateurs"],
          icon: "DatabaseIcon",
          mockup: "ERPMockup",
          color: "bg-indigo-500",
        },
        {
          title: "CRM",
          description: "Optimisez vos relations clients",
          features: ["Suivi prospects", "Automatisation", "Analytics"],
          icon: "UserCheckIcon",
          mockup: "CRMMockup",
          color: "bg-teal-500",
        },
        {
          title: "Application Mobile",
          description: "Développez votre app iOS et Android",
          features: ["Cross-platform", "Performance native", "Push notifications"],
          icon: "SmartphoneIcon",
          mockup: "MobileMockup",
          color: "bg-cyan-500",
        },
      ],
      processSteps: [
        { step: "01", title: "Analyse", description: "Étude de vos besoins et de votre marché" },
        { step: "02", title: "Conception", description: "Design et architecture sur-mesure" },
        { step: "03", title: "Développement", description: "Codage avec les dernières technologies" },
        { step: "04", title: "Lancement", description: "Mise en ligne et accompagnement" },
      ],
      companyValues: [
        {
          title: "Rapidité",
          description: "Livraison en 7 jours maximum. Nous respectons nos délais et optimisons chaque étape.",
          icon: "Speed",
          iconColor: "icon-blue"
        },
        {
          title: "Transparence",
          description: "Communication claire, tarifs affichés, suivi en temps réel de votre projet.",
          icon: "Transparency",
          iconColor: "icon-gold"
        },
        {
          title: "Technologies",
          description: "Stack moderne et performant : React, Vue, Node.js, Cloud, AI et dernières innovations.",
          icon: "Technology",
          iconColor: "icon-blue"
        },
        {
          title: "Prix Abordables",
          description: "Tarifs compétitifs sans compromis sur la qualité. Accessible aux PME africaines.",
          icon: "Price",
          iconColor: "icon-gold"
        }
      ],
      whyAdvantages: [
        {
          title: "Écoute Active",
          description: "Nous écoutons attentivement vos besoins pour comprendre vos défis spécifiques.",
          icon: "Listen"
        },
        {
          title: "Solutions Efficaces",
          description: "Chaque solution est pensée pour résoudre vos problèmes concrets et améliorer votre business.",
          icon: "Solutions"
        },
        {
          title: "Innovation Continue",
          description: "Nous utilisons les dernières technologies pour vous donner un avantage concurrentiel.",
          icon: "Innovation"
        },
        {
          title: "Engagement Total",
          description: "Votre succès est notre priorité. Nous vous accompagnons au-delà de la livraison.",
          icon: "Engagement"
        }
      ],
      portfolioProjects: [
        {
          title: "Restaurant Digital",
          description: "Plateforme de commande en ligne moderne avec gestion des réservations",
          image: "/resto.png",
          tags: ["Restaurant", "Commande", "Réservation"],
          featured: true,
          category: "website"
        },
        {
          title: "E-commerce Premium",
          description: "Boutique en ligne complète avec paiement intégré et gestion de stock",
          image: "/ecom.png",
          tags: ["E-commerce", "Boutique", "Paiement"],
          featured: true,
          category: "ecommerce"
        },
        {
          title: "Plateforme Événementielle",
          description: "Solution complète pour la gestion et promotion d'événements",
          image: "/event.png",
          tags: ["Événement", "Billetterie", "Promotion"],
          featured: true,
          category: "event"
        },
        {
          title: "Plateforme DGS",
          description: "Système de gestion moderne pour optimiser les processus administratifs",
          image: "/dgs1.png",
          tags: ["Dashboard", "Gestion", "Admin"],
          featured: true,
          category: "dashboard"
        },
        {
          title: "DGS Analytics",
          description: "Interface d'analyse avancée avec reporting en temps réel",
          image: "/dgs2.png",
          tags: ["Analytics", "Reporting", "BI"],
          featured: false,
          category: "dashboard"
        },
        {
          title: "Portail FED",
          description: "Plateforme web moderne pour la gestion des formations",
          image: "/fed1.png",
          tags: ["Formation", "E-learning", "Web"],
          featured: true,
          category: "website"
        },
        {
          title: "Dashboard FED",
          description: "Interface de gestion complète avec tableaux de bord interactifs",
          image: "/feddash.png",
          tags: ["Dashboard", "Management", "UI/UX"],
          featured: false,
          category: "dashboard"
        },
        {
          title: "Système SIGS",
          description: "Solution complète de gestion intégrée pour entreprises",
          image: "/sigs.png",
          tags: ["ERP", "Gestion", "Entreprise"],
          featured: true,
          category: "system"
        },
        {
          title: "Plateforme DSI",
          description: "Interface de direction des systèmes d'information",
          image: "/dsi.png",
          tags: ["DSI", "Management", "Tech"],
          featured: false,
          category: "dashboard"
        }
      ]
    }
  },
  methods: {
    openProject(project) {
      // Ouvrir le projet dans une nouvelle fenêtre ou modal
      console.log('Ouverture du projet:', project.title);
      // Ici vous pouvez ajouter la logique pour ouvrir le projet
      // window.open(project.url, '_blank') ou afficher une modal
    }
  }
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
  --primary-blue: #00B4D8;
  --primary-gold: #F59E0B;
  --accent-blue: #0077B6;
  --accent-gold: #D97706;
  --gray-50: #F8FAFC;
  --gray-100: #F1F5F9;
  --gray-200: #E2E8F0;
  --gray-300: #CBD5E1;
  --gray-600: #475569;
  --gray-700: #334155;
  --gray-800: #1E293B;
  --gray-900: #0F172A;
  --white: #FFFFFF;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  color: var(--gray-900);
  background: linear-gradient(to bottom right, var(--gray-50), #f0f9ff);
  min-height: 100vh;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Utility Classes */
.w-full { width: 100%; }
.h-full { height: 100%; }
.ml-2 { margin-left: 0.5rem; }

/* Header */
.header {
  border-bottom: 1px solid var(--gray-200);
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(8px);
  position: sticky;
  top: 0;
  z-index: 50;
}

.header-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 0;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-img {
  width: 32px;
  height: 32px;
}

.logo-text {
  font-size: 1.25rem;
  font-weight: bold;
  background: linear-gradient(to right, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}

.nav {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  color: var(--gray-700);
  text-decoration: none;
  transition: color 0.3s ease;
  font-weight: 500;
}

.nav-link:hover {
  color: var(--primary-blue);
}

/* Buttons */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 0.5rem;
  font-weight: 600;
  transition: all 0.3s ease;
  cursor: pointer;
  border: none;
  text-decoration: none;
  font-size: 0.875rem;
  padding: 0.5rem 1rem;
}

.btn-lg {
  font-size: 1rem;
  padding: 0.75rem 2rem;
}

.btn-primary {
  background: linear-gradient(to right, var(--primary-blue), var(--accent-blue));
  color: var(--white);
}

.btn-primary:hover {
  background: linear-gradient(to right, var(--accent-blue), var(--primary-blue));
  transform: translateY(-2px);
}

.btn-secondary {
  background: var(--white);
  color: var(--primary-blue);
  border: 1px solid var(--gray-200);
}

.btn-secondary:hover {
  background: var(--gray-50);
}

.btn-outline {
  background: transparent;
  border: 2px solid var(--gray-400);
  color: var(--gray-800);
}

.btn-outline:hover {
  background: var(--primary-blue);
  color: var(--white);
}

.btn-outline-white {
  background: transparent;
  border: 2px solid var(--white);
  color: var(--white);
}

.btn-outline-white:hover {
  background: var(--white);
  color: var(--primary-blue);
}

/* Hero Section */
.hero {
  padding: 5rem 0;
  background: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.5)), url('/agence.webp');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  min-height: 70vh;
}

.hero-content {
  text-align: center;
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
  padding: 2rem;
  width: 100%;
}

.hero-badge {
  display: inline-block;
  background: linear-gradient(45deg, rgba(0, 180, 216, 0.95), rgba(245, 158, 11, 0.95));
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 9999px;
  font-size: 0.95rem;
  margin-bottom: 1.5rem;
  backdrop-filter: blur(10px);
  border: 2px solid rgba(255, 255, 255, 0.4);
  font-weight: 600;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
}

.hero-title {
  font-size: 4.5rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  line-height: 1.1;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.9);
  background: rgba(0, 0, 0, 0.3);
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  backdrop-filter: blur(10px);
}

.hero-subtitle {
  font-size: 1.4rem;
  color: rgba(255, 255, 255, 0.95);
  margin-bottom: 2rem;
  max-width: 900px;
  margin-left: auto;
  margin-right: auto;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
  font-weight: 400;
}

.hero-cta {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  justify-content: center;
  margin-bottom: 3rem;
}

@media (min-width: 640px) {
  .hero-cta {
    flex-direction: row;
  }
}

.hero-cta .btn {
  font-size: 1.1rem;
  padding: 1rem 2rem;
  font-weight: 600;
}

.hero-stats {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.95);
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
  font-weight: 500;
}

.stat-item {
  display: flex;
  align-items: center;
  gap: 0.25rem;
}

.stat-item svg {
  color: #F59E0B;
  filter: drop-shadow(0 0 3px rgba(245, 158, 11, 0.5));
}

/* Values Section */
.values {
  padding: 5rem 0;
  background: var(--white);
}

.values-content {
  max-width: 1200px;
  margin: 0 auto;
}

.values-text {
  text-align: center;
  margin-bottom: 3rem;
}

.values-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: var(--gray-900);
}

.values-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.5;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

@media (min-width: 768px) {
  .values-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .values-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.value-card {
  text-align: center;
  padding: 2rem 1.5rem;
  background: var(--white);
  border-radius: 1rem;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.value-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-blue), var(--primary-gold));
  transition: left 0.5s ease;
}

.value-card:hover::before {
  left: 0;
}

.value-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.value-icon {
  width: 4rem;
  height: 4rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  transition: all 0.3s ease;
}

.icon-blue {
  background: linear-gradient(135deg, var(--primary-blue), var(--accent-blue));
  color: white;
}

.icon-gold {
  background: linear-gradient(135deg, var(--primary-gold), var(--accent-gold));
  color: white;
}

.value-card:hover .value-icon {
  transform: scale(1.1) rotate(5deg);
}

.value-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--gray-900);
}

.value-description {
  color: var(--gray-700);
  line-height: 1.6;
  font-size: 0.95rem;
}

/* Services Section */
.services {
  padding: 5rem 0;
  background: var(--white);
}

.services-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: var(--gray-900);
}

.services-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.5;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(520px, 1fr));
  gap: 2rem;
  max-width: 1400px;
  margin: 0 auto;
}

@media (min-width: 1024px) {
  .services-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (min-width: 1200px) {
  .services-grid {
    grid-template-columns: repeat(4, 1fr);
    gap: 2.5rem;
  }
}

.service-card {
  background: var(--white);
  border-radius: 0.75rem;
  transition: all 0.3s ease;
  border: 1px solid var(--gray-200);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.service-card:hover {
  box-shadow: 0 20px 25px rgba(0, 0, 0, 0.1);
  transform: translateY(-8px);
}

.service-mockup {
  height: 8rem;
  background: var(--gray-50);
  overflow: hidden;
}

.service-content {
  padding: 1.5rem;
}

.service-header {
  display: flex;
  align-items: center;
  margin-bottom: 0.75rem;
}

.service-icon {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 0.75rem;
  color: var(--white);
}

.bg-blue-500 { background: var(--primary-blue); }
.bg-green-500 { background: #10B981; }
.bg-purple-500 { background: #8B5CF6; }
.bg-orange-500 { background: var(--primary-gold); }
.bg-pink-500 { background: #EC4899; }
.bg-indigo-500 { background: #6366F1; }
.bg-teal-500 { background: #14B8A6; }
.bg-cyan-500 { background: #06B6D4; }

.service-title {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gray-900);
}

.service-description {
  color: var(--gray-700);
  font-size: 0.9rem;
  margin-bottom: 1rem;
  line-height: 1.5;
}

.service-features {
  list-style: none;
  margin-bottom: 1rem;
}

.service-features li {
  display: flex;
  align-items: center;
  font-size: 0.9rem;
  color: var(--gray-700);
  margin-bottom: 0.5rem;
  line-height: 1.4;
}

.service-features svg {
  color: #10B981;
  margin-right: 0.5rem;
  flex-shrink: 0;
}

.service-btn {
  width: 100%;
  transition: all 0.3s ease;
}

.service-card:hover .service-btn {
  background: var(--primary-blue);
  color: var(--white);
}

/* Portfolio Section */
.portfolio {
  padding: 5rem 0;
  background: linear-gradient(135deg, var(--gray-50) 0%, #f0f9ff 100%);
}

.portfolio-header {
  text-align: center;
  margin-bottom: 4rem;
}

.portfolio-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.5;
}

.portfolio-container-full {
  position: relative;
  margin-bottom: 4rem;
  width: 100vw;
  margin-left: calc(-49vw + 50%);
  padding: 0 2rem;
}

.portfolio-scroll {
  display: flex;
  gap: 1.5rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 1rem 0;
  -webkit-overflow-scrolling: touch;
}

.portfolio-scroll::-webkit-scrollbar {
  height: 8px;
}

.portfolio-scroll::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}

.portfolio-scroll::-webkit-scrollbar-thumb {
  background: linear-gradient(45deg, var(--primary-blue), var(--primary-gold));
  border-radius: 10px;
}

.portfolio-scroll::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(45deg, var(--accent-blue), var(--accent-gold));
}

.portfolio-card {
  position: relative;
  min-width: 320px;
  max-width: 320px;
  height: 280px;
  border-radius: 1rem;
  overflow: hidden;
  cursor: pointer;
  transition: all 0.4s ease;
  animation: slideInLeft 0.6s ease-out;
  flex-shrink: 0;
}

.portfolio-card:nth-child(1) { animation-delay: 0.1s; }
.portfolio-card:nth-child(2) { animation-delay: 0.2s; }
.portfolio-card:nth-child(3) { animation-delay: 0.3s; }
.portfolio-card:nth-child(4) { animation-delay: 0.4s; }
.portfolio-card:nth-child(5) { animation-delay: 0.5s; }
.portfolio-card:nth-child(6) { animation-delay: 0.6s; }

.portfolio-card:hover {
  transform: translateY(-12px) scale(1.02);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
  z-index: 10;
}

@media (max-width: 768px) {
  .portfolio-card {
    min-width: 280px;
    max-width: 280px;
    height: 240px;
  }
}

@media (min-width: 1400px) {
  .portfolio-card {
    min-width: 350px;
    max-width: 350px;
    height: 300px;
  }
  
  .portfolio-scroll {
    gap: 2rem;
  }
}

.portfolio-image {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.portfolio-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.portfolio-card:hover .portfolio-image img {
  transform: scale(1.08);
}

.portfolio-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(0, 180, 216, 0.9), rgba(245, 158, 11, 0.9));
  opacity: 0;
  transition: all 0.4s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
}

.portfolio-card:hover .portfolio-overlay {
  opacity: 1;
}

.portfolio-content {
  text-align: center;
  color: white;
  transform: translateY(20px);
  transition: transform 0.4s ease;
}

.portfolio-card:hover .portfolio-content {
  transform: translateY(0);
}

.portfolio-title {
  font-size: 1.4rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  line-height: 1.2;
}

.portfolio-description {
  font-size: 0.9rem;
  margin-bottom: 1rem;
  opacity: 0.9;
  line-height: 1.4;
}

.portfolio-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  justify-content: center;
  margin-bottom: 1.2rem;
}

.portfolio-tag {
  background: rgba(255, 255, 255, 0.2);
  padding: 0.25rem 0.75rem;
  border-radius: 9999px;
  font-size: 0.875rem;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.portfolio-cta {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  padding: 0.6rem 1.2rem;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 9999px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
}

.portfolio-cta:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.portfolio-stats {
  display: flex;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.stat-box {
  text-align: center;
  padding: 2rem;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 1rem;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  min-width: 150px;
  transition: all 0.3s ease;
}

.stat-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: bold;
  background: linear-gradient(45deg, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 1rem;
  color: var(--gray-700);
  font-weight: 500;
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
  }

/* Why Choose Us Section */
.why-choose-us {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f0f9ff 0%, var(--gray-50) 100%);
}

.why-content {
  max-width: 100%;
  margin: 0 auto;
}

.why-header {
  text-align: center;
  margin-bottom: 4rem;
}

.why-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 1rem auto 0;
  line-height: 1.5;
}

.why-grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 4rem;
  align-items: start;
}

@media (max-width: 1024px) {
  .why-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}

.mission-card {
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  border-radius: 1.5rem;
  padding: 3rem 2rem;
  color: white;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.mission-card::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(180deg); }
}

.mission-icon {
  width: 5rem;
  height: 5rem;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  backdrop-filter: blur(10px);
  border: 2px solid rgba(255, 255, 255, 0.3);
}

.mission-title {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.mission-description {
  font-size: 1rem;
  line-height: 1.6;
  opacity: 0.95;
}

.why-advantages {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}

.advantage-item {
  background: var(--white);
  border-radius: 1rem;
  padding: 1.5rem;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
  position: relative;
}

.advantage-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
  border-color: var(--primary-blue);
}

.advantage-icon {
  width: 3rem;
  height: 3rem;
  background: linear-gradient(135deg, #f0f9ff, #dbeafe);
  border-radius: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
  color: var(--primary-blue);
  transition: all 0.3s ease;
}

.advantage-item:hover .advantage-icon {
  background: linear-gradient(135deg, var(--primary-blue), var(--accent-blue));
  color: white;
  transform: scale(1.1);
}

.advantage-title {
  font-size: 1.125rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--gray-900);
}

.advantage-description {
  color: var(--gray-700);
  line-height: 1.5;
  font-size: 0.9rem;
}
  
  /* Process Section */
.process {
  padding: 5rem 0;
  background: linear-gradient(to right, var(--gray-50), #dbeafe);
}

.process-header {
  text-align: center;
  margin-bottom: 4rem;
}

.process-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  line-height: 1.5;
}

.process-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

@media (min-width: 768px) {
  .process-steps {
    grid-template-columns: repeat(4, 1fr);
  }
}

.process-step {
  text-align: center;
}

.step-number {
  width: 4rem;
  height: 4rem;
  background: linear-gradient(to right, var(--primary-blue), var(--primary-gold));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--white);
  font-weight: bold;
  font-size: 1.125rem;
  margin: 0 auto 1rem;
}

.step-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--gray-900);
}

.step-description {
  color: var(--gray-700);
  line-height: 1.5;
}

/* CTA Section */
.cta-section {
  padding: 5rem 0;
  background: linear-gradient(to right, var(--primary-blue), var(--primary-gold));
  color: var(--white);
}

.cta-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.cta-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.cta-subtitle {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  justify-content: center;
}

@media (min-width: 640px) {
  .cta-buttons {
    flex-direction: row;
  }
}

/* Footer */
.footer {
  background: var(--gray-900);
  color: var(--white);
  padding: 3rem 0;
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

@media (min-width: 768px) {
  .footer-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.footer-brand {
  max-width: none;
}

@media (min-width: 768px) {
  .footer-brand {
    max-width: 250px;
  }
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.footer-logo-img {
  width: 32px;
  height: 32px;
}

.footer-logo-text {
  font-size: 1.25rem;
  font-weight: bold;
}

.footer-description {
  color: var(--gray-300);
}

.footer-title {
  font-weight: 600;
  margin-bottom: 1rem;
}

.footer-links {
  list-style: none;
}

.footer-links li {
  margin-bottom: 0.5rem;
}

.footer-link {
  color: var(--gray-300);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: var(--white);
}

.footer-contact {
  list-style: none;
  color: var(--gray-300);
}

.footer-contact li {
  margin-bottom: 0.5rem;
}

.footer-bottom {
  border-top: 1px solid var(--gray-700);
  padding-top: 2rem;
  text-align: center;
  color: var(--gray-300);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .nav {
    display: none;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .process-steps {
    grid-template-columns: 1fr;
  }
  
  .footer-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 3rem 0;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .cta-title {
    font-size: 2rem;
  }
  
  .container {
    padding: 0 0.75rem;
  }
}
</style>