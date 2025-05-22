<script lang="ts">
  // No Svelte state needed for static embed
  // The script will be loaded in onMount
  import { onMount } from 'svelte';

  onMount(() => {
    // Load the UnicornStudio.js script dynamically
    if (!window.UnicornStudio) {
      const script = document.createElement('script');
      script.src = 'https://cdn.jsdelivr.net/gh/hiunicornstudio/unicornstudio.js@v1.4.20/dist/unicornStudio.umd.js';
      script.onload = () => {
        window.UnicornStudio.addScene({
          elementId: 'unicorn-hero',
          filePath: '/unicorn-studio/De_becker_code_hero.json',
          scale: 1,
          dpi: 1.5,
          altText: 'De Becker Code Hero Scene',
          ariaLabel: 'Unicorn Studio Hero Scene',
          production: false,
        });
      };
      document.head.appendChild(script);
    } else {
      window.UnicornStudio.addScene({
        elementId: 'unicorn-hero',
        filePath: '/unicorn-studio/De_becker_code_hero.json',
        scale: 1,
        dpi: 1.5,
        altText: 'De Becker Code Hero Scene',
        ariaLabel: 'Unicorn Studio Hero Scene',
        production: false,
      });
    }
  });
</script>

<style>
  /* Background canvas layer */
  #unicorn-hero-bg {
    position: absolute;
    inset: 0;
    z-index: -1;
    height: 100%;
    background: #f9f6e4;
    border-radius: 0;
    box-shadow: none;
    pointer-events: none;
    overflow: hidden;
  }
  #unicorn-hero {
    width: 100%;
    height: 100%;
  }

  /* Main content overlay */
  .main-content {
    position: relative;
    z-index: 2;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: stretch;
    color: #fff;
  }
  nav {
    position: absolute;
    width: 100%;
    padding-inline: 80px;
    top: 32px;
    display: flex;
    align-items: center;
    z-index: 3;
    justify-content: space-between;
  }
  .logo {
    flex-shrink: 0;
  }

  .logo img {
    height: 56px;
    width: auto;
    display: block;
  }
  .nav-links {
    display: flex;
    gap: 32px;
    background: rgba(255,255,255,0.24);
    backdrop-filter: blur(24px);
    border-radius: 12px;
    padding: 8px 32px;
  }
  .nav-links a {
    color: #fff;
    font-size: 1rem;
    font-weight: 400;
    text-decoration: none;
    letter-spacing: -0.03em;
    padding: 8px 0;
    transition: color 0.2s;
  }
  .nav-links a:hover {
    color: #53FF9D;
  }
  .hero, .hero-left, .hero-right, .subheadline, .headline, .cta-text, .cta-btn {
    /* font-family removed, now set globally */
  }
  .hero {
    position: relative;
    padding-top: 200px;
    padding-bottom: 8rem;
    padding-inline: 80px;
    display: flex;
    flex-direction: row;
    gap: 80px;
    width: 100%;
    align-items: end;
    min-height: 900px;
    overflow: hidden;
  }
  .hero-left {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    flex: 1 1 0;
    z-index: 1;
  }
  .subheadline {
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: 100%;
    letter-spacing: -2px;
    color: #FFF;
    margin-bottom: 80px;
    max-width: 655px;
  }
  .headline {
    font-size: 200px;
    font-style: normal;
    font-weight: 600;
    line-height: 100%; /* 200px */
    letter-spacing: -7px;
    color: #FFF;
    leading-trim: both;
    text-edge: cap;
    text-align: left;
    margin-bottom: -32px;
  }
  .hero-right {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 32px;
    margin-top: 60px;
    min-width: 232px;
    max-width: 260px;
    z-index: 1;
  }
  .cta-text {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 120%;
    letter-spacing: -1.3px;
    color: #FFF;
    margin-bottom: 24px;
    max-width: 232px;

    span {
      color: #42d97e;
    }
  }
  .cta-btn {
    background: #53FF9D;
    color: #042D14;
    font-size: 15.5px;
    font-weight: 700;
    border: none;
    border-radius: 12px;
    padding: 16px 40px;
    cursor: pointer;
    box-shadow: 0 2px 8px #0002;
    transition: background 0.2s, color 0.2s;
    line-height: 1.21;
    letter-spacing: -0.5px;
  }
  .cta-btn:hover {
    background: #53FF9D;
    color: #000;
  }

  @media (max-width: 900px) {
    .headline {
      font-size: 3rem;
    }
    .subheadline {
      font-size: 1.2rem;
    }
    .hero {
      padding-inline: 12px;
      padding-top: 60px;
    }
    .hero-right {
      flex-direction: column;
      gap: 16px;
    }
  }
</style>

<!-- Main overlay content -->
<div class="main-content">
  <!-- Standalone logo at top left -->
  <nav>
    <div class="logo">
      <img src="/dbc-logo.svg" alt="De Becker Code logo" />
    </div>
    <div class="nav-links">
      <a href="/">treatments</a>
      <a href="/">medical studies</a>
      <a href="/">concierge</a>
      <a href="/">corporate wellness</a>
    </div>
  </nav>
  <!-- Hero section with background canvas inside -->
  <section class="hero">
    <div class="hero-left">
      <div class="subheadline">Rewrite your future by merging ancient healing traditions with modern biometrics.</div>
      <h1 class="headline">Longevity<br />Redefined</h1>
    </div>
    <div class="hero-right">
      <div class="cta-text">Join the <br /><span>De Becker Code</span> movement and live beyond time.</div>
      <button class="cta-btn">Start Your Journey&nbsp;→</button>
    </div>
    <div id="unicorn-hero-bg">
      <div id="unicorn-hero"></div>
    </div>
  </section>
</div>

