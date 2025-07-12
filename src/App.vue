<template>
  <div id="app" class="min-h-screen bg-gradient-to-br from-slate-50 to-blue-50">
    <!-- Header -->
    <header class="header">
      <div class="container">
        <div class="header-content">
          <div class="logo" @click="navigateTo('home')" style="cursor: pointer;">
            <img src="/logo_light.png" alt="CIACEMS Technologies" class="logo-img" />
            <span class="logo-text">CIACEMS</span>
          </div>
          <nav class="nav">
            <a @click="navigateTo('home')" class="nav-link" :class="{ active: currentView === 'home' }">Accueil</a>
            <a @click="navigateTo('home', 'services')" class="nav-link">Services</a>
            <a @click="navigateTo('home', 'portfolio')" class="nav-link">Portfolio</a>
            <a @click="navigateTo('about')" class="nav-link" :class="{ active: currentView === 'about' }">À propos</a>
            <a @click="navigateTo('contact')" class="nav-link" :class="{ active: currentView === 'contact' }">Contact</a>
            <button @click="navigateTo('contact')" class="btn btn-primary">Devis gratuit</button>
          </nav>
        </div>
      </div>
    </header>

    <!-- Home Page -->
    <div v-if="currentView === 'home'">
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
                    <!-- <div class="portfolio-cta">
                      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/>
                        <polyline points="15,3 21,3 21,9"/>
                        <line x1="10" y1="14" x2="21" y2="3"/>
                      </svg>
                      <span>Voir le projet</span>
                    </div> -->
                  </div>
                </div>
              </div>
            </div>
        </div>
      </div>

      <div class="container">
        <div class="portfolio-stats">
          <div class="stat-box">
            <div class="stat-number">200+</div>
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
              <button @click="viewServiceDetails(service)" class="btn btn-outline service-btn">En savoir plus</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Budget & Pricing Section -->
    <section class="budget-pricing">
      <div class="container">
        <div class="budget-header">
          <h2 class="section-title">Parlons Budget & Tarifs</h2>
          <p class="budget-subtitle">
            Transparence totale sur nos tarifs. Soumettez votre budget pour une proposition personnalisée.
          </p>
        </div>

        <div class="budget-content">
          <!-- Pricing Section -->
          <div class="pricing-section">
            <div class="pricing-header">
              <h3 class="pricing-title">Nos Tarifs Transparents</h3>
              <p class="pricing-subtitle">À partir de 100 000 FCFA - Développement Web, Mobile, APIs & IA</p>
            </div>
            
            <div class="pricing-grid">
              <div class="pricing-card pricing-starter">
                <div class="pricing-badge">Populaire</div>
                <h4 class="pricing-name">Starter</h4>
                <div class="pricing-price">
                  <span class="price-amount">100 000</span>
                  <span class="price-currency">FCFA</span>
                </div>
                <ul class="pricing-features">
                  <li>Site vitrine 5 pages</li>
                  <li>Design responsive</li>
                  <li>SEO de base</li>
                  <li>Formulaire de contact</li>
                  <li>API simple intégrée</li>
                  <li>Hébergement 1 an</li>
                  <li>Support 3 mois</li>
                </ul>
                <button class="btn btn-outline pricing-btn">Choisir ce plan</button>
              </div>
              
              <div class="pricing-card pricing-pro">
                <div class="pricing-badge">Recommandé</div>
                <h4 class="pricing-name">Professional</h4>
                <div class="pricing-price">
                  <span class="price-amount">450 000</span>
                  <span class="price-currency">FCFA</span>
                </div>
                <ul class="pricing-features">
                  <li>Site/App jusqu'à 15 pages</li>
                  <li>Design sur mesure</li>
                  <li>SEO avancé</li>
                  <li>Animations & interactions</li>
                  <li>APIs personnalisées</li>
                  <li>Tableau de bord admin</li>
                  <li>Hébergement 1 an</li>
                  <li>Support 6 mois</li>
                </ul>
                <button class="btn btn-primary pricing-btn">Choisir ce plan</button>
              </div>
              
              <div class="pricing-card pricing-ai">
                <div class="pricing-badge">IA Incluse</div>
                <h4 class="pricing-name">IA Premium</h4>
                <div class="pricing-price">
                  <span class="price-amount">750 000</span>
                  <span class="price-currency">FCFA</span>
                </div>
                <ul class="pricing-features">
                  <li>Tout du plan Professional</li>
                  <li>Intégration IA avancée</li>
                  <li>Chatbot intelligent</li>
                  <li>Analyse prédictive</li>
                  <li>APIs IA personnalisées</li>
                  <li>Automatisation workflows</li>
                  <li>Formation IA incluse</li>
                  <li>Support prioritaire 1 an</li>
                </ul>
                <button class="btn btn-primary pricing-btn">Choisir ce plan</button>
              </div>
              
              <div class="pricing-card pricing-enterprise">
                <div class="pricing-badge">Entreprise</div>
                <h4 class="pricing-name">Enterprise</h4>
                <div class="pricing-price">
                  <span class="price-amount">Sur devis</span>
                  <span class="price-currency"></span>
                </div>
                <ul class="pricing-features">
                  <li>Solution complète</li>
                  <li>Architecture sur mesure</li>
                  <li>IA & APIs avancées</li>
                  <li>Intégrations entreprise</li>
                  <li>Formation équipe</li>
                  <li>Support prioritaire</li>
                  <li>Maintenance incluse</li>
                  <li>SLA garanti</li>
                </ul>
                <button class="btn btn-outline pricing-btn">Contactez-nous</button>
              </div>
            </div>
            
            <div class="subscription-section">
              <h4 class="subscription-title">Formules d'Abonnement Mensuel</h4>
              <div class="subscription-grid">
                <div class="subscription-card">
                  <div class="subscription-icon">
                    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                      <path d="M2 17l10 5 10-5"/>
                      <path d="M2 12l10 5 10-5"/>
                    </svg>
                  </div>
                  <h5 class="subscription-name">Maintenance Basic</h5>
                  <div class="subscription-price">25 000 FCFA<span>/mois</span></div>
                  <ul class="subscription-features">
                    <li>Mises à jour sécurité</li>
                    <li>Sauvegarde automatique</li>
                    <li>Support par email</li>
                  </ul>
                </div>
                
                <div class="subscription-card">
                  <div class="subscription-icon">
                    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/>
                      <polyline points="14,2 14,8 20,8"/>
                      <line x1="16" y1="13" x2="8" y2="13"/>
                      <line x1="16" y1="17" x2="8" y2="17"/>
                    </svg>
                  </div>
                  <h5 class="subscription-name">Growth</h5>
                  <div class="subscription-price">45 000 FCFA<span>/mois</span></div>
                  <ul class="subscription-features">
                    <li>Maintenance + ajouts</li>
                    <li>SEO mensuel</li>
                    <li>Rapports analytics</li>
                    <li>Support prioritaire</li>
                  </ul>
                </div>
                
                <div class="subscription-card">
                  <div class="subscription-icon">
                    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <circle cx="12" cy="12" r="10"/>
                      <path d="M8 12l2 2 4-4"/>
                    </svg>
                  </div>
                  <h5 class="subscription-name">Premium</h5>
                  <div class="subscription-price">85 000 FCFA<span>/mois</span></div>
                  <ul class="subscription-features">
                    <li>Support complet</li>
                    <li>Nouvelles fonctionnalités</li>
                    <li>Optimisations</li>
                    <li>Consulting stratégique</li>
                  </ul>
                </div>
                
                <div class="subscription-card">
                  <div class="subscription-icon">
                    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                      <path d="M2 17l10 5 10-5"/>
                      <path d="M2 12l10 5 10-5"/>
                    </svg>
                  </div>
                  <h5 class="subscription-name">IA Premium</h5>
                  <div class="subscription-price">120 000 FCFA<span>/mois</span></div>
                  <ul class="subscription-features">
                    <li>Maintenance IA incluse</li>
                    <li>Mise à jour modèles IA</li>
                    <li>Optimisation continue</li>
                    <li>Support expert IA</li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Form Section -->
          <div class="budget-form-section">
            <div class="budget-form-card">
              <h3 class="form-title">Partagez votre Budget</h3>
              <p class="form-description">
                Décrivez votre projet et votre budget. Nous vous proposerons la meilleure solution adaptée à vos moyens, incluant nos services de développement web, mobile, APIs et intelligence artificielle.
              </p>
              
              <form class="budget-form" @submit.prevent="submitBudget">
                <div class="form-grid">
                  <div class="form-group">
                    <label for="company" class="form-label">Nom de l'entreprise</label>
                    <input 
                      type="text" 
                      id="company" 
                      v-model="budgetForm.company"
                      class="form-input" 
                      placeholder="Votre entreprise"
                      required
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="email" class="form-label">Email</label>
                    <input 
                      type="email" 
                      id="email" 
                      v-model="budgetForm.email"
                      class="form-input" 
                      placeholder="votre@email.com"
                      required
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="phone" class="form-label">Téléphone</label>
                    <input 
                      type="tel" 
                      id="phone" 
                      v-model="budgetForm.phone"
                      class="form-input" 
                      placeholder="+225 XX XX XX XX"
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="project" class="form-label">Type de projet</label>
                    <select 
                      id="project" 
                      v-model="budgetForm.project"
                      class="form-select"
                      required
                    >
                      <option value="">Sélectionnez un type</option>
                      <option value="site-vitrine">Site Vitrine</option>
                      <option value="e-commerce">E-commerce</option>
                      <option value="application">Application Web</option>
                      <option value="mobile">Application Mobile</option>
                      <option value="api">Création d'API</option>
                      <option value="ia">Solution IA</option>
                      <option value="erp">Système ERP</option>
                      <option value="autre">Autre</option>
                    </select>
                  </div>
                  
                  <div class="form-group">
                    <label for="budget" class="form-label">Budget disponible (FCFA)</label>
                    <select 
                      id="budget" 
                      v-model="budgetForm.budget"
                      class="form-select"
                      required
                    >
                      <option value="">Choisissez votre budget</option>
                      <option value="100000-300000">100 000 - 300 000 FCFA</option>
                      <option value="300000-500000">300 000 - 500 000 FCFA</option>
                      <option value="500000-800000">500 000 - 800 000 FCFA</option>
                      <option value="800000-1500000">800 000 - 1 500 000 FCFA</option>
                      <option value="1500000+">Plus de 1 500 000 FCFA</option>
                    </select>
                  </div>
                  
                  <div class="form-group form-group-full">
                    <label for="description" class="form-label">Description du projet</label>
                    <textarea 
                      id="description" 
                      v-model="budgetForm.description"
                      class="form-textarea" 
                      placeholder="Décrivez votre projet et vos attentes (fonctionnalités, intégrations IA, APIs nécessaires...)..."
                      rows="4"
                      required
                    ></textarea>
                  </div>
                </div>
                
                <button type="submit" class="btn btn-primary btn-lg btn-full">
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="mr-2">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                  </svg>
                  Envoyer ma Proposition
                </button>
              </form>
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
    
    </div> <!-- End Home Page -->

    <!-- About Page -->
    <div v-if="currentView === 'about'">
      <section class="about-hero">
        <div class="container">
          <div class="about-hero-content">
            <h1 class="hero-title">À Propos de CIACEMS</h1>
            <p class="hero-subtitle">
              Cabinet d'ingénierie informatique et agence web premium dédiée à la transformation digitale des entreprises africaines.
            </p>
          </div>
        </div>
      </section>

      <section class="about-story">
        <div class="container">
          <div class="about-content">
            <div class="about-text">
              <h2 class="section-title">Notre Histoire</h2>
              <div class="story-content">
                <p>
                  Fondée avec la vision de démocratiser la digitalisation en Afrique, CIACEMS Technologies est née de la conviction 
                  que chaque entreprise africaine mérite d'avoir accès aux meilleures technologies numériques.
                </p>
                <p>
                  Nous sommes spécialisés dans le développement web, mobile, la création d'APIs et l'intégration d'intelligence artificielle. 
                  Notre équipe d'experts passionnés travaille avec des technologies de pointe pour offrir des solutions innovantes et sur-mesure.
                </p>
                <p>
                  En quelques années, nous avons accompagné plus de 100 entreprises dans leur transformation digitale, 
                  de la startup aux grandes organisations, en passant par les PME locales.
                </p>
              </div>
            </div>
            <div class="about-stats">
              <div class="stat-card">
                <div class="stat-number">200+</div>
                <div class="stat-label">Projets Réalisés</div>
              </div>
              <div class="stat-card">
                <div class="stat-number">100%</div>
                <div class="stat-label">Clients Satisfaits</div>
              </div>
              <div class="stat-card">
                <div class="stat-number">7 jours</div>
                <div class="stat-label">Délai Moyen</div>
              </div>
              <div class="stat-card">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Support</div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Gallery Section -->
      <section class="about-gallery">
        <div class="container">
          <div class="gallery-header">
            <h2 class="section-title">Dans les Coulisses</h2>
            <p class="gallery-subtitle">
              Découvrez l'univers CIACEMS : notre équipe passionnée, nos espaces de travail et nos moments de collaboration
            </p>
          </div>
          
          <div class="gallery-grid">
            <div class="gallery-item">
              <div class="gallery-image">
                <img src="/cis.jpeg" alt="Équipe CIACEMS au travail" />
                <div class="gallery-overlay">
                  <div class="gallery-content">
                    <h4 class="gallery-title">Notre Équipe</h4>
                    <p class="gallery-description">Des experts passionnés dédiés à votre réussite digitale</p>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="gallery-item">
              <div class="gallery-image">
                <img src="/nao.jpeg" alt="Espace de travail moderne" />
                <div class="gallery-overlay">
                  <div class="gallery-content">
                    <h4 class="gallery-title">Innovation</h4>
                    <p class="gallery-description">Un environnement propice à la créativité et à l'innovation</p>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="gallery-item">
              <div class="gallery-image">
                <img src="/po.jpeg" alt="Collaboration et brainstorming" />
                <div class="gallery-overlay">
                  <div class="gallery-content">
                    <h4 class="gallery-title">Collaboration</h4>
                    <p class="gallery-description">Travail d'équipe et échanges constructifs pour des solutions optimales</p>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="gallery-item">
              <div class="gallery-image">
                <img src="/po2.jpeg" alt="Développement et réalisation" />
                <div class="gallery-overlay">
                  <div class="gallery-content">
                    <h4 class="gallery-title">Excellence</h4>
                    <p class="gallery-description">Précision et attention aux détails dans chaque projet</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="about-mission">
        <div class="container">
          <div class="mission-grid">
            <div class="mission-item">
              <h3 class="mission-title">Notre Mission</h3>
              <p class="mission-text">
                Rendre accessible la transformation digitale aux entreprises africaines en proposant des solutions 
                technologiques innovantes, abordables et adaptées aux besoins locaux.
              </p>
            </div>
            <div class="mission-item">
              <h3 class="mission-title">Notre Vision</h3>
              <p class="mission-text">
                Devenir le partenaire digital de référence en Afrique, en contribuant à l'essor de l'économie numérique 
                et en aidant les entreprises à prospérer dans l'ère digitale.
              </p>
            </div>
            <div class="mission-item">
              <h3 class="mission-title">Nos Valeurs</h3>
              <p class="mission-text">
                Excellence, transparence, innovation et engagement. Nous croyons en la collaboration, 
                l'écoute active et la création de solutions qui génèrent un impact positif et durable.
              </p>
            </div>
          </div>
        </div>
      </section>

      <section class="about-team">
        <div class="container">
          <h2 class="section-title">Notre Expertise</h2>
          <div class="expertise-grid">
            <div class="expertise-card">
              <div class="expertise-icon">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="16 18 22 12 16 6"/>
                  <polyline points="8 6 2 12 8 18"/>
                </svg>
              </div>
              <h4 class="expertise-title">Développement Web</h4>
              <p class="expertise-text">React, Vue.js, Node.js, PHP, Python pour des applications web modernes et performantes.</p>
            </div>
            <div class="expertise-card">
              <div class="expertise-icon">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <rect x="5" y="2" width="14" height="20" rx="2" ry="2"/>
                  <line x1="12" y1="18" x2="12.01" y2="18"/>
                </svg>
              </div>
              <h4 class="expertise-title">Applications Mobile</h4>
              <p class="expertise-text">Développement iOS et Android natif ou cross-platform avec React Native et Flutter.</p>
            </div>
            <div class="expertise-card">
              <div class="expertise-icon">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                  <path d="M2 17l10 5 10-5"/>
                  <path d="M2 12l10 5 10-5"/>
                </svg>
              </div>
              <h4 class="expertise-title">APIs & Intégrations</h4>
              <p class="expertise-text">Conception et développement d'APIs REST, GraphQL et intégrations système complexes.</p>
            </div>
            <div class="expertise-card">
              <div class="expertise-icon">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M9 12l2 2 4-4"/>
                  <path d="M21 12c-1.4 0-4.5-1.1-6-3-1.5 1.9-4.6 3-6 3s-4.5-1.1-6-3c-1.5 1.9-4.6 3-6 3"/>
                  <path d="M21 21c-1.4 0-4.5-1.1-6-3-1.5 1.9-4.6 3-6 3s-4.5-1.1-6-3c-1.5 1.9-4.6 3-6 3"/>
                </svg>
              </div>
              <h4 class="expertise-title">Intelligence Artificielle</h4>
              <p class="expertise-text">Intégration d'IA, chatbots intelligents, analyse prédictive et automatisation.</p>
            </div>
          </div>
        </div>
      </section>
    </div>

    <!-- Contact Page -->
    <div v-if="currentView === 'contact'">
      <section class="contact-hero">
        <div class="container">
          <div class="contact-hero-content">
            <h1 class="hero-title">Contactez-Nous</h1>
            <p class="hero-subtitle">
              Prêt à transformer votre vision en réalité digitale ? Parlons de votre projet !
            </p>
          </div>
        </div>
      </section>

      <section class="contact-main">
        <div class="container">
          <div class="contact-grid">
            <div class="contact-form-section">
              <h2 class="contact-form-title">Démarrons Votre Projet</h2>
              <p class="contact-form-subtitle">
                Décrivez-nous votre projet et recevez un devis personnalisé sous 24h.
              </p>

              <form class="contact-form" @submit.prevent="submitContactForm">
                <div class="contact-form-grid">
                  <div class="form-group">
                    <label for="contact-name" class="form-label">Nom complet</label>
                    <input 
                      type="text" 
                      id="contact-name" 
                      v-model="contactForm.name"
                      class="form-input" 
                      placeholder="Votre nom complet"
                      required
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="contact-company" class="form-label">Entreprise</label>
                    <input 
                      type="text" 
                      id="contact-company" 
                      v-model="contactForm.company"
                      class="form-input" 
                      placeholder="Nom de votre entreprise"
                      required
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="contact-email" class="form-label">Email</label>
                    <input 
                      type="email" 
                      id="contact-email" 
                      v-model="contactForm.email"
                      class="form-input" 
                      placeholder="votre@email.com"
                      required
                    />
                  </div>
                  
                  <div class="form-group">
                    <label for="contact-phone" class="form-label">Téléphone</label>
                    <input 
                      type="tel" 
                      id="contact-phone" 
                      v-model="contactForm.phone"
                      class="form-input" 
                      placeholder="+225 XX XX XX XX"
                    />
                  </div>
                  
                  <div class="form-group form-group-full">
                    <label for="contact-service" class="form-label">Service souhaité</label>
                    <select 
                      id="contact-service" 
                      v-model="contactForm.service"
                      class="form-select"
                      required
                    >
                      <option value="">Sélectionnez un service</option>
                      <option value="site-vitrine">Site Vitrine</option>
                      <option value="e-commerce">E-commerce</option>
                      <option value="application-web">Application Web</option>
                      <option value="application-mobile">Application Mobile</option>
                      <option value="api">Développement d'API</option>
                      <option value="ia">Solution IA</option>
                      <option value="erp">Système ERP</option>
                      <option value="consulting">Consulting</option>
                      <option value="autre">Autre</option>
                    </select>
                  </div>
                  
                  <div class="form-group form-group-full">
                    <label for="contact-budget" class="form-label">Budget indicatif</label>
                    <select 
                      id="contact-budget" 
                      v-model="contactForm.budget"
                      class="form-select"
                    >
                      <option value="">Budget indicatif (optionnel)</option>
                      <option value="100000-300000">100 000 - 300 000 FCFA</option>
                      <option value="300000-500000">300 000 - 500 000 FCFA</option>
                      <option value="500000-800000">500 000 - 800 000 FCFA</option>
                      <option value="800000-1500000">800 000 - 1 500 000 FCFA</option>
                      <option value="1500000+">Plus de 1 500 000 FCFA</option>
                    </select>
                  </div>
                  
                  <div class="form-group form-group-full">
                    <label for="contact-message" class="form-label">Message</label>
                    <textarea 
                      id="contact-message" 
                      v-model="contactForm.message"
                      class="form-textarea" 
                      placeholder="Décrivez votre projet, vos objectifs et vos attentes..."
                      rows="5"
                      required
                    ></textarea>
                  </div>
                </div>
                
                <button type="submit" class="btn btn-primary btn-lg btn-full">
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="mr-2">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                  </svg>
                  Envoyer le Message
                </button>
              </form>
            </div>

            <div class="contact-info-section">
              <div class="contact-info">
                <h3 class="contact-info-title">Informations de Contact</h3>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                      <polyline points="22,6 12,13 2,6"/>
                    </svg>
                  </div>
                  <div class="contact-details">
                    <span class="contact-label">Email</span>
                    <span class="contact-value">alexkoffi0728@gmail.com</span>
                  </div>
                </div>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                    </svg>
                  </div>
                  <div class="contact-details">
                    <span class="contact-label">Téléphone</span>
                    <span class="contact-value">+225 07 49 12 34 56</span>
                  </div>
                </div>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                      <circle cx="12" cy="10" r="3"/>
                    </svg>
                  </div>
                  <div class="contact-details">
                    <span class="contact-label">Adresse</span>
                    <span class="contact-value">Abidjan, Côte d'Ivoire</span>
                  </div>
                </div>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <circle cx="12" cy="12" r="10"/>
                      <polyline points="12,6 12,12 16,14"/>
                    </svg>
                  </div>
                  <div class="contact-details">
                    <span class="contact-label">Horaires</span>
                    <span class="contact-value">Lun - Ven: 8h - 18h<br>Sam: 9h - 14h</span>
                  </div>
                </div>
              </div>
              
              <div class="contact-cta">
                <h4 class="cta-title">Besoin d'aide ?</h4>
                <p class="cta-text">
                  Notre équipe est là pour répondre à toutes vos questions et vous accompagner dans votre projet.
                </p>
                <div class="cta-buttons">
                  <button @click="navigateTo('home', 'services')" class="btn btn-outline">Voir nos Services</button>
                  <button @click="navigateTo('home', 'portfolio')" class="btn btn-secondary">Notre Portfolio</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

    <!-- Service Details View -->
    <div v-if="currentView === 'service-details'">
      <section class="service-details-hero">
        <div class="container">
          <div class="service-details-nav">
            <button @click="navigateTo('home', 'services')" class="back-button">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <polyline points="15,18 9,12 15,6"/>
              </svg>
              Retour aux Services
            </button>
          </div>
          <div class="service-details-header">
            <div class="service-details-icon" :class="selectedService?.color">
              <!-- Dynamic icon based on service -->
              <svg v-if="selectedService?.icon === 'GlobeIcon'" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <line x1="2" y1="12" x2="22" y2="12"/>
                <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/>
              </svg>
              
              <svg v-else-if="selectedService?.icon === 'ShoppingCartIcon'" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="9" cy="21" r="1"/>
                <circle cx="20" cy="21" r="1"/>
                <path d="m1 1 4 4 3.09 13.64A2 2 0 0 0 10 20h8.21a2 2 0 0 0 1.91-1.36L22 10H6"/>
              </svg>
              
              <!-- Add other icons as needed -->
            </div>
            <h1 class="hero-title">{{ selectedService?.title }}</h1>
            <p class="hero-subtitle">{{ selectedService?.description }}</p>
          </div>
        </div>
      </section>

      <section class="service-details-content" v-if="selectedService">
        <div class="container">
          <div class="service-details-grid">
            <div class="service-main-content">
              <div class="service-overview">
                <h2 class="section-title">Vue d'ensemble</h2>
                <p class="service-overview-text">{{ getServiceOverview(selectedService) }}</p>
              </div>

              <div class="service-features-detailed">
                <h3 class="features-title">Fonctionnalités Incluses</h3>
                <div class="features-list">
                  <div v-for="(feature, index) in getDetailedFeatures(selectedService)" :key="index" class="feature-item">
                    <div class="feature-icon">
                      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M9 12l2 2 4-4"/>
                        <circle cx="12" cy="12" r="10"/>
                      </svg>
                    </div>
                    <div class="feature-content">
                      <h4 class="feature-name">{{ feature.name }}</h4>
                      <p class="feature-description">{{ feature.description }}</p>
                    </div>
                  </div>
                </div>
              </div>

              <div class="service-process">
                <h3 class="process-title">Notre Processus</h3>
                <div class="process-steps-detailed">
                  <div v-for="(step, index) in getServiceProcess(selectedService)" :key="index" class="process-step-detailed">
                    <div class="step-number">{{ index + 1 }}</div>
                    <div class="step-content">
                      <h4 class="step-title">{{ step.title }}</h4>
                      <p class="step-description">{{ step.description }}</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="service-sidebar">
              <div class="service-pricing-card">
                <h3 class="pricing-card-title">Tarifs & Délais</h3>
                <div class="pricing-info">
                  <div class="price-range">
                    <span class="price-from">À partir de</span>
                    <span class="price-amount">{{ getServicePrice(selectedService) }}</span>
                  </div>
                  <div class="delivery-time">
                    <span class="delivery-label">Délai de livraison</span>
                    <span class="delivery-value">{{ getServiceDelivery(selectedService) }}</span>
                  </div>
                </div>
                <button @click="navigateTo('contact')" class="btn btn-primary btn-full">
                  Demander un Devis
                </button>
              </div>

              <div class="service-technologies">
                <h4 class="technologies-title">Technologies Utilisées</h4>
                <div class="technologies-list">
                  <span v-for="tech in getServiceTechnologies(selectedService)" :key="tech" class="tech-tag">
                    {{ tech }}
                  </span>
                </div>
              </div>

              <div class="service-related">
                <h4 class="related-title">Services Complémentaires</h4>
                <div class="related-services">
                  <div v-for="related in getRelatedServices(selectedService)" :key="related.title" 
                       @click="viewServiceDetails(related)" 
                       class="related-service-item">
                    <span class="related-service-name">{{ related.title }}</span>
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <polyline points="9,18 15,12 9,6"/>
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

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
              <li><a @click="navigateTo('about')" class="footer-link">À propos</a></li>
              <li><a @click="navigateTo('home', 'portfolio')" class="footer-link">Portfolio</a></li>
              <li><a href="#" class="footer-link">Blog</a></li>
              <li><a @click="navigateTo('contact')" class="footer-link">Contact</a></li>
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
      currentView: 'home',
      selectedService: null,
      budgetForm: {
        company: '',
        email: '',
        phone: '',
        project: '',
        budget: '',
        description: ''
      },
      contactForm: {
        name: '',
        company: '',
        email: '',
        phone: '',
        service: '',
        budget: '',
        message: ''
      },
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
          description: "Stack moderne et performant : React, Vue, Node.js, Fluttter, Django, Docker, Cloud, AI et dernières innovations.",
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
          title: "Système SIGS",
          description: "Solution complète de gestion intégrée du Sport en Côte d'Ivoire",
          image: "/sigs.png",
          tags: ["ERP", "Gestion", "Sport"],
          featured: true,
          category: "system"
        },
        {
          title: "Tableau de bord DGS",
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
          title: "Portail des Fédérations sportives",
          description: "Plateforme web moderne pour la gestion des Fédérations sportives",
          image: "/fed1.png",
          tags: ["Fédération", "Sport", "Web"],
          featured: true,
          category: "website"
        },
        {
          title: "Tableau de bord FED",
          description: "Interface de gestion complète avec tableaux de bord interactifs",
          image: "/feddash.png",
          tags: ["Dashboard", "Management", "UI/UX"],
          featured: false,
          category: "dashboard"
        },
        
        {
          title: "Plateforme DSI",
          description: "Interface de la direction des systèmes d'information",
          image: "/dsi.png",
          tags: ["DSI", "Management", "Tech"],
          featured: false,
          category: "dashboard"
        }
      ]
    }
  },
  methods: {
    navigateTo(view, section = null) {
      this.currentView = view;
      if (section && view === 'home') {
        // Scroll to section after view change
        this.$nextTick(() => {
          const element = document.getElementById(section);
          if (element) {
            element.scrollIntoView({ behavior: 'smooth' });
          }
        });
      }
    },
    viewServiceDetails(service) {
      this.selectedService = service;
      this.currentView = 'service-details';
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    openProject(project) {
      // Ouvrir le projet dans une nouvelle fenêtre ou modal
      console.log('Ouverture du projet:', project.title);
      // Ici vous pouvez ajouter la logique pour ouvrir le projet
      // window.open(project.url, '_blank') ou afficher une modal
    },
    submitContactForm() {
      // Validation basique
      if (!this.contactForm.name || !this.contactForm.company || !this.contactForm.email || !this.contactForm.service || !this.contactForm.message) {
        alert('Veuillez remplir tous les champs obligatoires');
        return;
      }

      // Préparation du contenu de l'email
      const subject = encodeURIComponent(`Nouvelle demande de contact - ${this.contactForm.company}`);
      const body = encodeURIComponent(`
Bonjour,

Nouvelle demande de contact depuis le site web CIACEMS.

INFORMATIONS CLIENT:
- Nom: ${this.contactForm.name}
- Entreprise: ${this.contactForm.company}
- Email: ${this.contactForm.email}
- Téléphone: ${this.contactForm.phone || 'Non renseigné'}

DÉTAILS DE LA DEMANDE:
- Service souhaité: ${this.contactForm.service}
- Budget indicatif: ${this.contactForm.budget || 'Non précisé'}
- Message: ${this.contactForm.message}

Merci de traiter cette demande rapidement.

Cordialement,
Site Web CIACEMS
      `);

      // Ouverture du client email
      const mailtoLink = `mailto:alexkoffi0728@gmail.com?subject=${subject}&body=${body}`;
      window.location.href = mailtoLink;

      // Réinitialisation du formulaire après envoi
      this.contactForm = {
        name: '',
        company: '',
        email: '',
        phone: '',
        service: '',
        budget: '',
        message: ''
      };

      // Message de confirmation
      alert('Votre message a été préparé et votre client email va s\'ouvrir. Merci pour votre confiance !');
    },
    getServiceOverview(service) {
      const overviews = {
        'Site Vitrine': 'Un site vitrine professionnel pour présenter votre entreprise, vos services et établir votre crédibilité en ligne. Design moderne, optimisé pour tous les appareils et référencement naturel inclus.',
        'E-commerce': 'Boutique en ligne complète avec système de paiement sécurisé, gestion des stocks, interface d\'administration et outils marketing intégrés pour développer vos ventes.',
        'Blog': 'Plateforme de publication avec système de gestion de contenu intuitif, optimisation SEO, gestion des commentaires et newsletter pour engager votre audience.',
        'Landing Page': 'Page d\'atterrissage optimisée pour la conversion avec design persuasif, formulaires de capture, A/B testing et analytics pour maximiser vos résultats.',
        'Site Événementiel': 'Solution complète pour organiser et promouvoir vos événements avec billetterie en ligne, gestion des inscriptions et promotion automatisée.',
        'ERP': 'Système de gestion intégré pour digitaliser tous vos processus métier, de la comptabilité à la gestion client en passant par les stocks et ressources humaines.',
        'CRM': 'Plateforme de gestion de la relation client pour optimiser vos ventes, automatiser le suivi des prospects et analyser les performances commerciales.',
        'Application Mobile': 'Application mobile native ou cross-platform pour iOS et Android, avec interface utilisateur moderne et intégrations avancées.'
      };
      return overviews[service.title] || 'Solution digitale sur-mesure adaptée à vos besoins spécifiques.';
    },
    getDetailedFeatures(service) {
      const features = {
        'Site Vitrine': [
          { name: 'Design Responsive', description: 'Interface adaptée à tous les écrans (mobile, tablette, desktop)' },
          { name: 'SEO Optimisé', description: 'Référencement naturel pour être visible sur Google' },
          { name: 'Formulaire de Contact', description: 'Système de contact intégré avec notifications' },
          { name: 'Hébergement Inclus', description: '1 an d\'hébergement professionnel offert' },
          { name: 'SSL & Sécurité', description: 'Certificat SSL et sécurisation complète' },
          { name: 'Analytics', description: 'Suivi des performances et statistiques détaillées' }
        ],
        'E-commerce': [
          { name: 'Catalogue Produits', description: 'Gestion complète des produits avec variantes et options' },
          { name: 'Paiement Sécurisé', description: 'Intégration Orange Money, Wave, cartes bancaires' },
          { name: 'Gestion des Stocks', description: 'Suivi automatique des stocks et alertes' },
          { name: 'Interface Admin', description: 'Tableau de bord pour gérer commandes et clients' },
          { name: 'Marketing Tools', description: 'Codes promo, newsletter, remarketing' },
          { name: 'Livraison', description: 'Gestion des zones et frais de livraison' }
        ],
        'Application Mobile': [
          { name: 'Cross-Platform', description: 'Une seule app pour iOS et Android' },
          { name: 'Performance Native', description: 'Vitesse et fluidité optimales' },
          { name: 'Push Notifications', description: 'Notifications en temps réel pour vos utilisateurs' },
          { name: 'Intégrations API', description: 'Connexion avec vos systèmes existants' },
          { name: 'Offline Mode', description: 'Fonctionnalités disponibles hors ligne' },
          { name: 'Store Publication', description: 'Publication sur App Store et Play Store' }
        ]
      };
      return features[service.title] || [
        { name: 'Solution Sur-Mesure', description: 'Développement adapté à vos besoins spécifiques' },
        { name: 'Technologies Modernes', description: 'Stack technique à la pointe de l\'innovation' },
        { name: 'Support Technique', description: 'Accompagnement et support continu' }
      ];
    },
    getServiceProcess(service) {
      return [
        { title: 'Analyse des Besoins', description: 'Étude approfondie de vos objectifs et contraintes techniques' },
        { title: 'Conception & Design', description: 'Création des maquettes et architecture de votre solution' },
        { title: 'Développement', description: 'Codage avec méthodologie agile et tests continus' },
        { title: 'Tests & Validation', description: 'Tests complets et validation avec votre équipe' },
        { title: 'Déploiement', description: 'Mise en ligne et configuration de production' },
        { title: 'Formation & Support', description: 'Formation de vos équipes et support post-lancement' }
      ];
    },
    getServicePrice(service) {
      const prices = {
        'Site Vitrine': '100 000 FCFA',
        'E-commerce': '200 000 FCFA',
        'Blog': '100 000 FCFA',
        'Landing Page': '100 000 FCFA',
        'Site Événementiel': '200 000 FCFA',
        'ERP': '800 000 FCFA',
        'CRM': '600 000 FCFA',
        'Application Mobile': '750 000 FCFA'
      };
      return prices[service.title] || 'Sur devis';
    },
    getServiceDelivery(service) {
      const deliveries = {
        'Site Vitrine': '5-7 jours',
        'E-commerce': '10-14 jours',
        'Blog': '3-5 jours',
        'Landing Page': '2-3 jours',
        'Site Événementiel': '7-10 jours',
        'ERP': '3-6 mois',
        'CRM': '1-3 mois',
        'Application Mobile': '4-8 semaines'
      };
      return deliveries[service.title] || '2-4 semaines';
    },
    getServiceTechnologies(service) {
      const technologies = {
        'Site Vitrine': ['Vue.js', 'HTML5', 'CSS3', 'JavaScript', 'Python'],
        'E-commerce': ['Vue.js', 'Node.js', 'Django', 'Stripe', 'PayPal', 'MySQL', 'etc'],
        'Blog': ['WordPress', 'Django', 'MySQL', 'PostgreSQL', 'JavaScript', 'etc'],
        'Landing Page': ['Vue.js', 'React', 'Tailwind CSS', 'JavaScript'],
        'Site Événementiel': ['Vue.js', 'Node.js', 'Calendar API', 'Payment Gateway'],
        'ERP': ['Vue.js', 'Node.js', 'Django', 'PostgreSQL', 'Redis', 'Docker'],
        'CRM': ['Vue.js', 'Node.js', 'Django', 'MySQL', 'Chart.js', 'Email APIs'],
        'Application Mobile': ['React Native', 'JavaScript', 'Flutter', 'Redux', 'Firebase', 'etc']
      };
      return technologies[service.title] || ['Vue.js', 'Node.js', 'Django', 'MySQL', 'PostgreSQL', 'Redis', 'Docker', 'etc'];
    },
    getRelatedServices(service) {
      const related = {
        'Site Vitrine': ['Landing Page', 'Blog', 'E-commerce'],
        'E-commerce': ['Site Vitrine', 'CRM', 'Application Mobile'],
        'Application Mobile': ['E-commerce', 'CRM', 'ERP'],
        'ERP': ['CRM', 'Site Vitrine', 'Application Mobile']
      };
      const relatedTitles = related[service.title] || ['Site Vitrine', 'E-commerce'];
      return this.websiteTypes.filter(s => relatedTitles.includes(s.title) && s.title !== service.title);
    },
    submitBudget() {
      // Validation basique
      if (!this.budgetForm.company || !this.budgetForm.email || !this.budgetForm.project || !this.budgetForm.budget || !this.budgetForm.description) {
        alert('Veuillez remplir tous les champs obligatoires');
        return;
      }

      // Préparation du contenu de l'email
      const subject = encodeURIComponent(`Nouvelle demande de devis - ${this.budgetForm.company}`);
      const body = encodeURIComponent(`
Bonjour,

Je vous contacte pour soumettre une demande de devis pour un projet digital.

INFORMATIONS ENTREPRISE:
- Nom: ${this.budgetForm.company}
- Email: ${this.budgetForm.email}
- Téléphone: ${this.budgetForm.phone || 'Non renseigné'}

DÉTAILS DU PROJET:
- Type: ${this.budgetForm.project}
- Budget disponible: ${this.budgetForm.budget} FCFA
- Description: ${this.budgetForm.description}

Merci de me faire parvenir une proposition adaptée à mes besoins et à mon budget.

Cordialement,
${this.budgetForm.company}
      `);

      // Ouverture du client email
      const mailtoLink = `mailto:alexkoffi0728@gmail.com?subject=${subject}&body=${body}`;
      window.location.href = mailtoLink;

      // Réinitialisation du formulaire après envoi
      this.budgetForm = {
        company: '',
        email: '',
        phone: '',
        project: '',
        budget: '',
        description: ''
      };

      // Message de confirmation
      alert('Votre demande de devis a été préparée et votre client email va s\'ouvrir. Merci pour votre confiance !');
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
  cursor: pointer;
}

.nav-link:hover {
  color: var(--primary-blue);
}

.nav-link.active {
  color: var(--primary-blue);
  font-weight: 600;
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
  animation: fadeInUp 0.8s ease-out 0.2s both;
}

.hero-title {
  font-size: 5rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  line-height: 1.1;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.9);
  background: rgba(0, 0, 0, 0.3);
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  backdrop-filter: blur(10px);
  animation: fadeInUp 1s ease-out 0.6s both;
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
  animation: fadeInUp 1s ease-out 1.2s both;
}

.hero-cta {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  justify-content: center;
  margin-bottom: 3rem;
  animation: fadeInUp 1s ease-out 1.8s both;
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
  animation: fadeInUp 1s ease-out 2.4s both;
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
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold), var(--accent-blue));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
  text-align: center;
  line-height: 1.2;
  position: relative;
  animation: gradient-shift 3s ease-in-out infinite;
  background-size: 200% 200%;
}

.values-subtitle {
  font-size: 1.4rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
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
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold), var(--accent-blue));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
  text-align: center;
  line-height: 1.2;
  position: relative;
  animation: gradient-shift 3s ease-in-out infinite;
  background-size: 200% 200%;
}

.services-subtitle {
  font-size: 1.4rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
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
  font-size: 1.4rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
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
  font-size: 1.4rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 1rem auto 0;
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
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

@keyframes gradient-shift {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
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
  font-size: 1.4rem;
  color: var(--gray-700);
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
  max-width: 700px;
  margin: 0 auto;
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
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1rem;
  text-align: center;
  line-height: 1.2;
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
  cursor: pointer;
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

/* Budget & Pricing Section */
.budget-pricing {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f0f9ff 0%, var(--white) 50%, #fef3c7 100%);
}

.budget-header {
  text-align: center;
  margin-bottom: 4rem;
}

.budget-subtitle {
  font-size: 1.4rem;
  color: var(--gray-700);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
  font-weight: 400;
  text-align: center;
}

.budget-content {
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

.pricing-section {
  width: 100%;
}

.budget-form-section {
  max-width: 1000px;
  margin: 0 auto;
  width: 100%;
}

/* Form Section */
.budget-form-section {
  position: relative;
}

.budget-form-card {
  background: var(--white);
  border-radius: 1.5rem;
  padding: 2.5rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  border: 1px solid var(--gray-200);
  position: relative;
  overflow: hidden;
}

.budget-form-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-blue), var(--primary-gold));
}

.form-title {
  font-size: 1.75rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}

.form-description {
  color: var(--gray-700);
  margin-bottom: 2rem;
  line-height: 1.6;
}

.form-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}

@media (min-width: 768px) {
  .form-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

.form-group {
  margin-bottom: 0;
}

.form-group-full {
  grid-column: 1 / -1;
}

.form-label {
  display: block;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
}

.form-input, .form-select, .form-textarea {
  width: 100%;
  padding: 0.75rem 1rem;
  border: 2px solid var(--gray-200);
  border-radius: 0.75rem;
  font-size: 1rem;
  transition: all 0.3s ease;
  background: var(--white);
  color: var(--gray-900);
}

.form-input:focus, .form-select:focus, .form-textarea:focus {
  outline: none;
  border-color: var(--primary-blue);
  box-shadow: 0 0 0 3px rgba(0, 180, 216, 0.1);
}

.form-select {
  cursor: pointer;
  background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3e%3cpolyline points='6,9 12,15 18,9'%3e%3c/polyline%3e%3c/svg%3e");
  background-repeat: no-repeat;
  background-position: right 0.75rem center;
  background-size: 1rem;
  padding-right: 2.5rem;
}

.form-textarea {
  resize: vertical;
  min-height: 100px;
}

.btn-full {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1rem;
}

.mr-2 {
  margin-right: 0.5rem;
}

/* Pricing Section */
.pricing-section {
  position: relative;
}

.pricing-header {
  text-align: center;
  margin-bottom: 3rem;
}

.pricing-title {
  font-size: 2rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}

.pricing-subtitle {
  font-size: 1.125rem;
  color: var(--gray-700);
  font-weight: 500;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-bottom: 3rem;
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
}

@media (min-width: 768px) {
  .pricing-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 767px) {
  .pricing-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .pricing-grid {
    grid-template-columns: 1fr;
  }
}

.pricing-card {
  background: var(--white);
  border-radius: 1.5rem;
  padding: 1.5rem;
  border: 2px solid var(--gray-200);
  position: relative;
  transition: all 0.3s ease;
  text-align: center;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.pricing-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.pricing-starter {
  border-color: var(--primary-blue);
}

.pricing-pro {
  border-color: var(--primary-gold);
}

.pricing-ai {
  border-color: #8B5CF6;
  background: linear-gradient(135deg, #f8fafc 0%, #f3f4f6 100%);
}

.pricing-enterprise {
  border-color: var(--gray-300);
}

.pricing-badge {
  position: absolute;
  top: -10px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  color: white;
  padding: 0.5rem 1.5rem;
  border-radius: 1rem;
  font-size: 0.875rem;
  font-weight: 600;
}

.pricing-starter .pricing-badge {
  background: var(--primary-blue);
}

.pricing-pro .pricing-badge {
  background: var(--primary-gold);
}

.pricing-ai .pricing-badge {
  background: #8B5CF6;
}

.pricing-enterprise .pricing-badge {
  background: var(--gray-600);
}

.pricing-name {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--gray-900);
  margin: 1.5rem 0 1rem;
}

.pricing-price {
  margin-bottom: 2rem;
}

.price-amount {
  font-size: 2.5rem;
  font-weight: bold;
  color: var(--gray-900);
}

.price-currency {
  font-size: 1.125rem;
  color: var(--gray-600);
  font-weight: 500;
}

.pricing-features {
  list-style: none;
  margin-bottom: 2rem;
  text-align: left;
  flex-grow: 1;
}

.pricing-features li {
  padding: 0.4rem 0;
  color: var(--gray-700);
  position: relative;
  padding-left: 1.5rem;
  font-size: 0.9rem;
  line-height: 1.4;
}

.pricing-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--primary-blue);
  font-weight: bold;
}

.pricing-ai .pricing-features li::before {
  color: #8B5CF6;
}

.pricing-btn {
  width: 100%;
  margin-top: auto;
}

/* Subscription Section */
.subscription-section {
  background: var(--gray-50);
  padding: 3rem 2rem;
  border-radius: 1.5rem;
  margin-top: 3rem;
}

.subscription-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--gray-900);
  text-align: center;
  margin-bottom: 2rem;
}

.subscription-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5rem;
}

@media (min-width: 768px) {
  .subscription-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 767px) {
  .subscription-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .subscription-grid {
    grid-template-columns: 1fr;
  }
}

.subscription-card {
  background: var(--white);
  padding: 2rem 1.5rem;
  border-radius: 1rem;
  text-align: center;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
}

.subscription-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.subscription-icon {
  width: 4rem;
  height: 4rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  margin: 0 auto 1rem;
}

.subscription-name {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
}

.subscription-price {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--primary-blue);
  margin-bottom: 1rem;
}

.subscription-price span {
  font-size: 1rem;
  color: var(--gray-600);
  font-weight: 500;
}

.subscription-features {
  list-style: none;
  text-align: left;
}

.subscription-features li {
  padding: 0.25rem 0;
  color: var(--gray-700);
  font-size: 0.9rem;
  position: relative;
  padding-left: 1.5rem;
}

.subscription-features li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: var(--primary-gold);
  font-weight: bold;
}

/* About Page Styles */
.about-hero {
  padding: 6rem 0 4rem;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--primary-gold) 100%);
  color: white;
  text-align: center;
}

.about-hero-content .hero-title {
  color: white;
  background: none;
  -webkit-text-fill-color: white;
}

.about-story {
  padding: 5rem 0;
  background: var(--white);
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

@media (max-width: 1024px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}

.story-content p {
  font-size: 1.125rem;
  line-height: 1.8;
  color: var(--gray-700);
  margin-bottom: 1.5rem;
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
}

.stat-card {
  background: linear-gradient(135deg, var(--gray-50), #f0f9ff);
  padding: 2rem 1.5rem;
  border-radius: 1rem;
  text-align: center;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.about-mission {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f0f9ff 0%, var(--gray-50) 100%);
}

.mission-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.mission-item {
  background: var(--white);
  padding: 2.5rem 2rem;
  border-radius: 1.5rem;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
}

.mission-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.mission-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 1rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}

.mission-text {
  color: var(--gray-700);
  line-height: 1.7;
  font-size: 1rem;
}

.about-gallery {
  padding: 5rem 0;
  background: linear-gradient(135deg, var(--gray-50) 0%, #f0f9ff 100%);
}

.gallery-header {
  text-align: center;
  margin-bottom: 3rem;
}

.gallery-subtitle {
  font-size: 1.25rem;
  color: var(--gray-700);
  max-width: 600px;
  margin: 1rem auto 0;
  line-height: 1.6;
  font-weight: 400;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

@media (min-width: 768px) {
  .gallery-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .gallery-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.gallery-item {
  position: relative;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  transition: all 0.4s ease;
  background: var(--white);
}

.gallery-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.gallery-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
}

.gallery-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.gallery-item:hover .gallery-image img {
  transform: scale(1.05);
}

.gallery-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(0, 180, 216, 0.9), rgba(245, 158, 11, 0.9));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.4s ease;
  backdrop-filter: blur(2px);
}

.gallery-item:hover .gallery-overlay {
  opacity: 1;
}

.gallery-content {
  text-align: center;
  color: white;
  padding: 1.5rem;
  transform: translateY(20px);
  transition: transform 0.4s ease;
}

.gallery-item:hover .gallery-content {
  transform: translateY(0);
}

.gallery-title {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.gallery-description {
  font-size: 0.9rem;
  line-height: 1.4;
  opacity: 0.95;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.about-team {
  padding: 5rem 0;
  background: var(--white);
}

.expertise-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.expertise-card {
  background: var(--white);
  padding: 2rem;
  border-radius: 1rem;
  border: 1px solid var(--gray-200);
  text-align: center;
  transition: all 0.3s ease;
}

.expertise-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.expertise-icon {
  width: 5rem;
  height: 5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  margin: 0 auto 1.5rem;
}

.expertise-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 1rem;
}

.expertise-text {
  color: var(--gray-700);
  line-height: 1.6;
}

/* Contact Page Styles */
.contact-hero {
  padding: 6rem 0 4rem;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--primary-gold) 100%);
  color: white;
  text-align: center;
}

.contact-hero-content .hero-title {
  color: white;
  background: none;
  -webkit-text-fill-color: white;
}

.contact-main {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f0f9ff 0%, var(--white) 50%, #fef3c7 100%);
}

.contact-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 4rem;
  align-items: start;
}

@media (max-width: 1024px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}

.contact-form-title {
  font-size: 2rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}

.contact-form-subtitle {
  color: var(--gray-700);
  margin-bottom: 2rem;
  line-height: 1.6;
  font-size: 1.125rem;
}

.contact-form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}

@media (max-width: 768px) {
  .contact-form-grid {
    grid-template-columns: 1fr;
  }
}

.contact-info {
  background: var(--white);
  border-radius: 1.5rem;
  padding: 2.5rem;
  border: 1px solid var(--gray-200);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  margin-bottom: 2rem;
}

.contact-info-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 2rem;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.contact-icon {
  width: 3rem;
  height: 3rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  border-radius: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.contact-label {
  font-weight: 600;
  color: var(--gray-900);
  font-size: 0.9rem;
}

.contact-value {
  color: var(--gray-700);
  line-height: 1.5;
}

.contact-cta {
  background: linear-gradient(135deg, #f0f9ff, #dbeafe);
  border-radius: 1.5rem;
  padding: 2rem;
  text-align: center;
}

.cta-title {
  font-size: 1.25rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
}

.cta-text {
  color: var(--gray-700);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

@media (min-width: 640px) {
  .cta-buttons {
    flex-direction: row;
    justify-content: center;
  }
}

/* Service Details Styles */
.service-details-hero {
  padding: 6rem 0 4rem;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--primary-gold) 100%);
  color: white;
}

.service-details-nav {
  margin-bottom: 2rem;
}

.back-button {
  background: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.75rem;
  font-weight: 500;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
  cursor: pointer;
}

.back-button:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateX(-5px);
}

.service-details-header {
  text-align: center;
}

.service-details-icon {
  width: 5rem;
  height: 5rem;
  border-radius: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  margin: 0 auto 2rem;
}

.service-details-header .hero-title {
  color: white;
  background: none;
  -webkit-text-fill-color: white;
}

.service-details-content {
  padding: 5rem 0;
  background: var(--white);
}

.service-details-grid {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

@media (max-width: 1024px) {
  .service-details-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}

.service-overview {
  margin-bottom: 3rem;
}

.service-overview-text {
  font-size: 1.125rem;
  line-height: 1.8;
  color: var(--gray-700);
}

.service-features-detailed {
  margin-bottom: 3rem;
}

.features-title, .process-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 2rem;
}

.features-list {
  display: grid;
  gap: 1.5rem;
}

.feature-item {
  display: flex;
  gap: 1rem;
  padding: 1.5rem;
  background: var(--gray-50);
  border-radius: 1rem;
  border: 1px solid var(--gray-200);
  transition: all 0.3s ease;
}

.feature-item:hover {
  background: #f0f9ff;
  border-color: var(--primary-blue);
}

.feature-icon {
  width: 2.5rem;
  height: 2.5rem;
  background: var(--primary-blue);
  border-radius: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.feature-name {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
}

.feature-description {
  color: var(--gray-700);
  line-height: 1.6;
}

.process-steps-detailed {
  display: grid;
  gap: 2rem;
}

.process-step-detailed {
  display: flex;
  gap: 1.5rem;
  align-items: flex-start;
}

.step-number {
  width: 3rem;
  height: 3rem;
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-gold));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: bold;
  flex-shrink: 0;
}

.step-content h4 {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 0.5rem;
}

.step-content p {
  color: var(--gray-700);
  line-height: 1.6;
}

.service-sidebar {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.service-pricing-card {
  background: var(--white);
  border-radius: 1.5rem;
  padding: 2rem;
  border: 2px solid var(--primary-blue);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.pricing-card-title {
  font-size: 1.25rem;
  font-weight: bold;
  color: var(--gray-900);
  margin-bottom: 1.5rem;
  text-align: center;
}

.pricing-info {
  text-align: center;
  margin-bottom: 2rem;
}

.price-range {
  margin-bottom: 1rem;
}

.price-from {
  display: block;
  font-size: 0.875rem;
  color: var(--gray-600);
  margin-bottom: 0.25rem;
}

.price-amount {
  font-size: 2rem;
  font-weight: bold;
  color: var(--primary-blue);
}

.delivery-time {
  padding-top: 1rem;
  border-top: 1px solid var(--gray-200);
}

.delivery-label {
  display: block;
  font-size: 0.875rem;
  color: var(--gray-600);
  margin-bottom: 0.25rem;
}

.delivery-value {
  font-weight: 600;
  color: var(--gray-900);
}

.service-technologies {
  background: var(--gray-50);
  border-radius: 1rem;
  padding: 1.5rem;
  border: 1px solid var(--gray-200);
}

.technologies-title, .related-title {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gray-900);
  margin-bottom: 1rem;
}

.technologies-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  background: var(--primary-blue);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 500;
}

.service-related {
  background: var(--white);
  border-radius: 1rem;
  padding: 1.5rem;
  border: 1px solid var(--gray-200);
}

.related-services {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.related-service-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.75rem;
  border-radius: 0.5rem;
  border: 1px solid var(--gray-200);
  cursor: pointer;
  transition: all 0.3s ease;
}

.related-service-item:hover {
  background: #f0f9ff;
  border-color: var(--primary-blue);
}

.related-service-name {
  font-weight: 500;
  color: var(--gray-900);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-title {
    font-size: 3rem;
  }
  
  .hero-subtitle {
    font-size: 1rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .values-title {
    font-size: 2.5rem;
  }
  
  .pricing-title {
    font-size: 1.75rem;
  }
  
  .pricing-grid {
    grid-template-columns: 1fr !important;
  }
  
  .subscription-grid {
    grid-template-columns: 1fr !important;
  }
  
  .form-grid {
    grid-template-columns: 1fr !important;
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
    font-size: 2.5rem;
  }
  
  .cta-title {
    font-size: 2.5rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .values-title {
    font-size: 2rem;
  }
  
  .pricing-title {
    font-size: 1.5rem;
  }
  
  .budget-form-card {
    padding: 1.5rem;
  }
  
  .subscription-section {
    padding: 2rem 1rem;
  }
  
  .form-grid {
    gap: 1rem;
  }
  
  .budget-form-card {
    padding: 1.5rem;
  }
  
  .about-stats {
    grid-template-columns: 1fr;
  }
  
  .contact-form-grid {
    grid-template-columns: 1fr !important;
  }
  
  .service-details-grid {
    grid-template-columns: 1fr !important;
  }
  
  .stat-card {
    padding: 1.5rem 1rem;
  }
  
  .expertise-grid {
    grid-template-columns: 1fr;
  }
  
  .mission-grid {
    grid-template-columns: 1fr;
  }
  
  .container {
    padding: 0 0.75rem;
  }
}

/* Animation keyframes pour les effets de fondu */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes slideInLeft {
  0% {
    opacity: 0;
    transform: translateX(-30px);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  0% {
    opacity: 0;
    transform: translateX(30px);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

</style>