/* ==========================================================================
   1. CSS Reset & Variables
   ========================================================================== */
:root {
  --primary-color: #3b82f6;
  --primary-hover: #1d4ed8;
  --accent-color: #6366f1;
  --bg-color: #0b0f19;
  --card-bg: #111827;
  --card-border: rgba(255, 255, 255, 0.08);
  --text-main: #f9fafb;
  --text-muted: #9ca3af;
  --gradient-brand: linear-gradient(135deg, #3b82f6 0%, #6366f1 100%);
  --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.2);
  --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.4);
  --transition-fast: all 0.25s ease-in-out;
}

*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  background-color: var(--bg-color);
  color: var(--text-main);
  line-height: 1.6;
  overflow-x: hidden;
}

a {
  text-decoration: none;
  color: inherit;
  transition: var(--transition-fast);
}

ul {
  list-style: none;
}

/* ==========================================================================
   2. Base & Typography
   ========================================================================== */
.section {
  padding: 80px 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 50px;
}

.section-header h2 {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 12px;
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.section-header p {
  color: var(--text-muted);
  font-size: 1.05rem;
}

/* Buttons */
.btn {
  display: inline-block;
  padding: 12px 28px;
  font-size: 0.95rem;
  font-weight: 600;
  border-radius: 8px;
  cursor: pointer;
  transition: var(--transition-fast);
  border: none;
}

.btn-primary {
  background: var(--gradient-brand);
  color: #ffffff;
  box-shadow: 0 4px 14px rgba(59, 130, 246, 0.35);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(59, 130, 246, 0.5);
}

.btn-outline {
  background: transparent;
  color: var(--text-main);
  border: 1px solid var(--card-border);
}

.btn-outline:hover {
  background-color: rgba(255, 255, 255, 0.05);
  border-color: var(--primary-color);
}

/* ==========================================================================
   3. Header & Navigation (Flexbox)
   ========================================================================== */
.header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(11, 15, 25, 0.85);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--card-border);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 16px 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: -0.5px;
}

.logo span {
  color: var(--primary-color);
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 32px;
}

.nav-link {
  font-size: 0.95rem;
  color: var(--text-muted);
  font-weight: 500;
  position: relative;
  padding-bottom: 4px;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0%;
  height: 2px;
  bottom: 0;
  left: 0;
  background: var(--gradient-brand);
  transition: var(--transition-fast);
}

.nav-link:hover {
  color: var(--text-main);
}

.nav-link:hover::after {
  width: 100%;
}

/* ==========================================================================
   4. Hero Section (Flexbox)
   ========================================================================== */
.hero-section {
  max-width: 1200px;
  margin: 40px auto 0;
  padding: 80px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
}

.hero-content {
  flex: 1 1 550px;
}

.hero-title {
  font-size: 3rem;
  line-height: 1.2;
  font-weight: 700;
  margin-bottom: 20px;
}

.hero-subtitle {
  color: var(--text-muted);
  font-size: 1.15rem;
  margin-bottom: 32px;
  max-width: 500px;
}

.hero-actions {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.hero-card {
  flex: 1 1 380px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  background: var(--card-bg);
  padding: 32px;
  border-radius: 16px;
  border: 1px solid var(--card-border);
  box-shadow: var(--shadow-lg);
}

.stat-badge {
  background: rgba(255, 255, 255, 0.03);
  padding: 16px 20px;
  border-radius: 12px;
  border-left: 4px solid var(--primary-color);
}

.stat-badge h3 {
  font-size: 1.6rem;
  color: var(--primary-color);
}

.stat-badge p {
  color: var(--text-muted);
  font-size: 0.9rem;
}

/* ==========================================================================
   5. Card Layouts: Services, Features, Team (Flexbox)
   ========================================================================== */
.grid-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}

.card {
  flex: 1 1 calc(33.333% - 24px);
  min-width: 280px;
  background-color: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  padding: 32px;
  box-shadow: var(--shadow-sm);
  transition: var(--transition-fast);
}

.card:hover {
  transform: translateY(-6px);
  border-color: rgba(59, 130, 246, 0.4);
  box-shadow: var(--shadow-lg);
}

.card-icon {
  font-size: 2rem;
  margin-bottom: 16px;
}

.card h3 {
  font-size: 1.25rem;
  margin-bottom: 12px;
}

.card p {
  color: var(--text-muted);
  font-size: 0.95rem;
}

/* Features */
.features-section {
  background-color: rgba(255, 255, 255, 0.015);
  border-radius: 20px;
}

.feature-card h4 {
  font-size: 1.15rem;
  margin-bottom: 10px;
  color: var(--text-main);
}

/* Team */
.team-card {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.avatar-placeholder {
  width: 72px;
  height: 72px;
  border-radius: 50%;
  background: var(--gradient-brand);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  font-weight: 700;
  margin-bottom: 16px;
}

.role {
  color: var(--primary-color);
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 10px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* ==========================================================================
   6. Contact Section (Flexbox Form)
   ========================================================================== */
.contact-section {
  max-width: 650px;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  background: var(--card-bg);
  padding: 36px;
  border-radius: 16px;
  border: 1px solid var(--card-border);
  box-shadow: var(--shadow-sm);
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-group label {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--text-muted);
}

.form-group input,
.form-group textarea {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid var(--card-border);
  border-radius: 8px;
  padding: 12px 16px;
  color: var(--text-main);
  font-size: 0.95rem;
  font-family: inherit;
  transition: var(--transition-fast);
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--primary-color);
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.2);
}

.form-btn {
  width: 100%;
  margin-top: 8px;
}

/* ==========================================================================
   7. Footer Section (Flexbox)
   ========================================================================== */
.footer {
  border-top: 1px solid var(--card-border);
  background: #070a11;
  padding: 48px 24px 32px;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 24px;
}

.footer-brand p {
  color: var(--text-muted);
  font-size: 0.85rem;
  margin-top: 4px;
}

.footer-links {
  display: flex;
  gap: 24px;
}

.footer-links a {
  color: var(--text-muted);
  font-size: 0.9rem;
}

.footer-links a:hover {
  color: var(--text-main);
}

.footer-copy {
  color: var(--text-muted);
  font-size: 0.85rem;
}

/* ==========================================================================
   8. Responsive Media Queries
   ========================================================================== */

/* Tablets (577px - 992px) */
@media screen and (max-width: 992px) {
  .hero-section {
    flex-direction: column;
    text-align: center;
    padding: 40px 20px;
  }

  .hero-actions {
    justify-content: center;
  }

  .hero-card {
    width: 100%;
  }

  .card {
    flex: 1 1 calc(50% - 24px);
  }
}

/* Mobile Devices (<= 576px) */
@media screen and (max-width: 576px) {
  .nav-container {
    flex-direction: column;
    gap: 14px;
  }

  .nav-links {
    gap: 16px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .nav-btn {
    display: none;
  }

  .hero-title {
    font-size: 2.1rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .card {
    flex: 1 1 100%;
  }

  .section {
    padding: 50px 16px;
  }

  .contact-form {
    padding: 24px 16px;
  }

  .footer-container {
    flex-direction: column;
    text-align: center;
    gap: 20px;
  }

  .footer-links {
    flex-wrap: wrap;
    justify-content: center;
  }
}
