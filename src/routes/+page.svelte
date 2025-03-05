<script>
  import { onMount } from 'svelte';
  import { page } from '$app/stores';
  import { Home, User, Github, MessageSquare, Mail, MessageCircle, MapPin, Menu } from 'lucide-svelte';

  $: currentPath = $page.url.pathname;

  let activeLink = '';
  let mobileMenuOpen = false;

  function handleClick(link) {
      activeLink = link;
      setTimeout(() => {
          activeLink = '';
      }, 300); // Duration of the scale effect
      
      // Close mobile menu when a link is clicked
      if (mobileMenuOpen) {
          mobileMenuOpen = false;
      }
  }

  function toggleMobileMenu() {
    console.log('Toggle menu:', !mobileMenuOpen);
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<div class="layout">
  <div class="mobile-header">
    <div class="mobile-profile">
      <img src="topographic-textures.jpg" alt="Profile" style="width: 32px; height: 32px; border-radius: 50%; object-fit: cover; border: 1px solid #fff;">
      <span class="mobile-name">yan5q</span>
    </div>
    <button class="menu-toggle" on:click={toggleMobileMenu}>
      <Menu size={24} />
    </button>
  </div>

  <div class="mobile-nav" class:mobile-nav-open={mobileMenuOpen}>
    <nav class="mobile-nav-links">
      <a href="/" class="nav-link" class:active={currentPath === '/'} on:click={() => handleClick('home')}>
        <Home size={16} />
        <span>Home</span>
      </a>
      <a href="/about" class="nav-link" class:active={currentPath === '/about'} on:click={() => handleClick('about')}>
        <User size={16} />
        <span>About</span>
      </a>
      <a href="https://github.com/Ondraaasek" class="nav-link" on:click={() => handleClick('github')}>
        <Github size={16} />
        <span>Github</span>
      </a>
      <a href="https://discord.com/users/yan5q" class="nav-link" on:click={() => handleClick('discord')}>
        <MessageSquare size={16} />
        <span>Discord</span>
      </a>
      <a href="mailto:yan5q@yan5q.org" class="nav-link" on:click={() => handleClick('email')}>
        <Mail size={16} />
        <span>Email</span>
      </a>
      <a href="https://matrix.to/#/@yan5q:matrix.org" class="nav-link" on:click={() => handleClick('matrix')}>
        <MessageCircle size={16} />
        <span>Matrix</span>
      </a>
    </nav>
  </div>

  <aside class="sidebar"> 
    <div class="profile">
      <img src="topographic-textures.jpg" alt="u arent supposed to see this text, if u see it, the host is probably down " style="width: 40px; height: 40px; border-radius: 50%; object-fit: cover; border: 1px solid #fff; box-shadow: 0 0 10px rgba(0,0,0,0.1);">
      <div class="profile-info">
        <h4 class="profile-name">yan5q</h4>
        <p class="profile-title">Student & Developer</p>
      </div>
    </div>

    <nav class="nav-links">
      <a href="/" class="nav-link" class:active={currentPath === '/'} class:active-link={activeLink === 'home'} on:click={() => handleClick('home')}>
        <Home size={16} />
        <span>Home</span>
      </a>
      <a href="/about" class="nav-link" class:active={currentPath === '/about'} class:active-link={activeLink === 'about'} on:click={() => handleClick('about')}>
        <User size={16} />
        <span>About</span>
      </a>
      <a href="https://github.com/Ondraaasek" class="nav-link" class:active-link={activeLink === 'github'} on:click={() => handleClick('github')}>
        <Github size={16} />
        <span>Github</span>
      </a>
      <a href="https://discord.com/users/yan5q" class="nav-link" class:active-link={activeLink === 'discord'} on:click={() => handleClick('discord')}>
        <MessageSquare size={16} />
        <span>Discord</span>
      </a>
      <a href="mailto:yan5q@yan5q.org" class="nav-link" class:active-link={activeLink === 'email'} on:click={() => handleClick('email')}>
        <Mail size={16} />
        <span>Email</span>
      </a>
      <a href="https://matrix.to/#/@yan5q:matrix.org" class="nav-link" class:active-link={activeLink === 'matrix'} on:click={() => handleClick('matrix')}>
        <MessageCircle size={16} />
        <span>Matrix</span>
      </a>
    </nav>
  </aside>

  <main class="container">
    <section class="intro">
      <p class="location fade-in">
        <MapPin size={14} />
        Prague, Czech Republic
      </p>
      <h1 class="fade-in">Hey, I'm yan5q</h1>
      <p class="intro-text fade-in">
        I'm a cybersecurity student from Czech Republic, who likes learning new stuff, 
        coding, traveling, I'm currently learning C#, want to learn Rust, and my main focus is front-end development.
      </p>
    </section>

    <section class="content fade-in">
      <div class="section">
        <h2>My technologies</h2>
        <div class="tech-stack">
          <button class="tech-item button-csharp" class:active-link={activeLink === 'csharp'} on:click={() => handleClick('csharp')}>
            <img src="https://cdn.worldvectorlogo.com/logos/c--4.svg" alt="C# logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">C#</span>
              <span class="tech-description">Java but MS</span>
            </div>
          </button>
          <button class="tech-item button-svelte" class:active-link={activeLink === 'svelte'} on:click={() => handleClick('svelte')}>
            <img src="https://cdn.worldvectorlogo.com/logos/svelte-1.svg" alt="Svelte logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">Svelte</span>
              <span class="tech-description">UI framework</span>
            </div>
          </button>
          <button class="tech-item button-html" class:active-link={activeLink === 'html'} on:click={() => handleClick('html')}>
            <img src="https://cdn.worldvectorlogo.com/logos/html-1.svg" alt="HTML logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">HTML</span>
              <span class="tech-description">Markup lang</span>
            </div>
          </button>
          <button class="tech-item button-css" class:active-link={activeLink === 'css'} on:click={() => handleClick('css')}>
            <img src="https://cdn.worldvectorlogo.com/logos/css-3.svg" alt="CSS logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">CSS</span>
              <span class="tech-description">Just CSS</span>
            </div>
          </button>
          <button class="tech-item button-js" class:active-link={activeLink === 'javascript'} on:click={() => handleClick('javascript')}>
            <img src="https://cdn.worldvectorlogo.com/logos/logo-javascript.svg" alt="JavaScript logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">JavaScript</span>
              <span class="tech-description">Scripting lang</span>
            </div>
          </button>
          <button class="tech-item button-json" class:active-link={activeLink === 'json'} on:click={() => handleClick('json')}>
            <img src="https://cdn.worldvectorlogo.com/logos/json.svg" alt="JSON logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">JSON</span>
              <span class="tech-description">Data format</span>
            </div>
          </button>
          <button class="tech-item button-python" class:active-link={activeLink === 'python'} on:click={() => handleClick('python')}>
            <img src="https://cdn.worldvectorlogo.com/logos/python-5.svg" alt="Python logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">Python</span>
              <span class="tech-description">Basic lang</span>
            </div>
          </button>
          <button class="tech-item button-swift" class:active-link={activeLink === 'swift'} on:click={() => handleClick('swift')}>
            <img src="https://cdn.worldvectorlogo.com/logos/swift-15.svg" alt="Swift logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">Swift</span>
              <span class="tech-description">Apple stuff</span>
            </div>
          </button>
          <button class="tech-item button-git" class:active-link={activeLink === 'git'} on:click={() => handleClick('git')}>
            <img src="https://cdn.worldvectorlogo.com/logos/git-icon.svg" alt="Git logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">Git</span>
              <span class="tech-description">Version control</span>
            </div>
          </button>
          <button class="tech-item button-cursor" class:active-link={activeLink === 'vscode'} on:click={() => handleClick('vscode')}>
            <img src="https://paulstamatiou.com/_next/image?url=%2Fgear%2Fcursor-app-icon.png&w=3840&q=75" alt="Cursor logo" class="tech-icon" />
            <div class="tech-text">
              <span class="tech-name">Cursor</span>
              <span class="tech-description">IDE w/ AI</span>
            </div>
          </button>
        </div>
      </div>
      
      <div class="section">
        <h2>My projects</h2>
        <div class="projects-list">
            <div class="project-wrapper">
                <button class="project-item button-svelte">
                    <img src="https://cdn.worldvectorlogo.com/logos/svelte-1.svg" alt="Svelte logo" class="project-icon" />
                    <div class="project-text">
                        <span class="project-name">yan5q.org</span>
                        <span class="project-description">my personal site</span>
                    </div>
                </button>
            </div>
            <div class="project-wrapper">
                <button class="project-item button-python">
                    <img src="https://cdn.worldvectorlogo.com/logos/python-5.svg" alt="Python logo" class="project-icon" />
                    <div class="project-text">
                        <span class="project-name">AutoCertificate</span>
                        <span class="project-description">preparation courses</span>
                    </div>
                </button>
            </div>
            <div class="project-wrapper">
                <button class="project-item">
                    <img src="https://cdn.worldvectorlogo.com/logos/unity-69.svg" alt="Unity logo" class="project-icon" />
                    <div class="project-text">
                        <span class="project-name">SSPSliminal</span>
                        <span class="project-description">liminal game</span>
                    </div>
                </button>
            </div>
        </div>
      </div>
    </section>

    <footer>
      <hr>
      <div class="footer-content">
        <h3>yan5q </h3>
        <p>Student and Developer • 2024 <span class="version-tag" style="float: right; background-color: #222222; padding-left:0.2rem; padding-right:0.2rem; border-radius: 5px;"><code>release version 2.2</code></span></p>
      </div>
    </footer>
  </main>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    min-height: 100vh;
    background-color: #171717;
    color: #e2e8f0;
    font-family: "Geist", monospace;
    /*font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;*/
  }

  .layout {
    display: flex;
    min-height: 100vh;
  }

  .sidebar {
    width: 16rem;
    padding: 6rem 2rem;
    border-right: 1px solid #262626;
    position: fixed;
    height: 100vh;
    background-color: #171717;
    box-sizing: border-box;
  }

  .nav-links {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  .nav-link {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.875rem;
    padding: 0.75rem 0.875rem;
    border-radius: 0.5rem;
    transition: transform 0.3s ease, background-color 0.3s ease, color 0.3s ease;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    position: relative;
    transition: transform 0.3s ease;
  }

  .nav-link:hover {
    color: #f8fafc;
    background-color: #262626;
    transition: all 0.3s ease;
  }

  .nav-link:active {
    transform: scale(0.9);
  }

  .nav-link.active,
  .nav-link.active-link {
    color: #f8fafc;
    background-color: #262626;
    transform: scale(1);
  }

  .nav-link.active::before {
    content: '';
    position: absolute;
    left: -2rem;
    top: 50%;
    transform: translateY(-50%);
    width: 3px;
    height: 1rem;
    background-color: #f8fafc;
    border-radius: 0 3px 3px 0;
    transition: all 0.3s ease;
  }

  .container {
    flex: 1;
    max-width: 640px;
    padding: 4rem 1.5rem;
    margin: 0 auto;
     margin-left: calc(16rem + 4rem); /*sidebar width + some spacing */
}

  .location {
    color: #94a3b8;
    font-size: 0.875rem;
    margin-bottom: 1rem;
  }

  .intro {
    margin-bottom: 4rem;
  }

  .intro-text {
    font-size: 1.125rem;
    line-height: 1.75;
    color: #94a3b8;
    margin-top: 1.5rem;
  }

  h1 {
    font-size: 2.25rem;
    font-weight: 700;
    margin: 0;
    color: #f8fafc;
  }

  h2 {
    font-size: 1.5rem;
    font-weight: 600;
    color: #f1f5f9;
    margin: 2rem 0 1rem 0;
  }

  h3 {
    font-size: 1.25rem;
    font-weight: 600;
    color: #f1f5f9;
    margin: 1rem 0;
  }

  .tech-stack {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 0.5rem;
    align-items: center;
  }

  .tech-item {
    background-color: #262626;
    color: #e2e8f0;
    padding: 0.25rem;
    border-radius: 0.375rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: transform 0.3s ease, background-color 0.3s ease;
    min-width: 170px;
    height: 50px;
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    /*outline: 3px;
    outline-color: #ffffff;
    outline-width: 3px;*/
  }

  .tech-item:hover {
    transform: translateY(-2.15px);
    /*background-color: #3b3b3b;*/
  }

  .tech-item:active {
    transform: scale(0.9);
  }

  .tech-icon {
    width: 30px;
    height: 30px;
    padding: 10px;
  }

  .tech-text {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .tech-name {
    font-size: 1.125rem;
    font-weight: bold;
  }

  .tech-description {
    font-size: 0.75rem;
    color: #94a3b8;
  }
  .project {
    background-color: #262626;
    color: #e2e8f0;
    padding: 0rem;
    border-radius: 0.375rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 0.25rem;
    transition: transform 0.3s ease, background-color 0.3s ease;
    min-width: 255px;
    /*height: 70px;*/
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    /*outline: 3px;
    outline-color: #ffffff;
    outline-width: 3px;*/
    padding-left: 15px;
    padding-right: 15px;
    position: relative;
    overflow: hidden;
  }
  
  .project::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 8px;
    height: 100%;
    opacity: 0.7;
  }
  
  .project-web::before {
    background-color: #ff3e00; /* Svelte color */
  }
  
  .project-python::before {
    background-color: #3776AB; /* Python color */
  }
  
  .project-unity::before {
    background-color: #44A8B3; /* Unity-ish teal color */
  }
  
  .project:hover {
    transform: translateY(-2.15px);
    /*background-color: #3b3b3b;*/
  }

  .project:active {
    transform: scale(0.9);
  }
  .projects-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0.5rem;
    margin-top: 1rem;
  }

  .project-wrapper {
    width: 100%;
  }

  .project-item {
    background-color: #262626;
    color: #e2e8f0;
    padding: 0.25rem;
    border-radius: 0.375rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: transform 0.3s ease, background-color 0.3s ease;
    min-width: 170px;
    /*height: 50px;*/
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    width: 100%;
  }

  .project-icon {
    width: 30px;
    height: 30px;
    padding: 10px;
  }

  .project-name {
    font-size: 1.125rem;
    font-weight: bold;
    margin-bottom: 0;
  }

  .project-description {
    font-size: 0.75rem;
    color: #94a3b8;
  }

  footer {
    margin-top: 4rem;
    color: #64748b;
    font-size: 0.875rem;
  }

  hr {
    border: none;
    border-top: 1px solid #262626;
    margin: 2rem 0;
  }

  @media (max-width: 768px) {
    .sidebar {
      display: none;
    }

    .mobile-header {
      display: flex !important;
    }

    .mobile-nav {
      height: auto;
      max-height: calc(100vh - 60px);
      overflow-y: auto;
    }

    .container {
      margin-left: 0;
      padding: 4rem 1rem;
      padding-top: 80px;
      max-width: 100%;
      overflow-x: hidden;
    }

    .tech-stack {
      grid-template-columns: repeat(2, 1fr);
      gap: 0.75rem;
    }

    .projects-list {
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .tech-item, .project-item {
      min-width: 0;
      width: 100%;
    }

    h1 {
      font-size: 2rem;
    }

    .intro-text {
      font-size: 1rem;
    }

    .mobile-nav-links {
      padding: 0.5rem;
      background-color: rgba(23, 23, 23, 0.95);
    }
  }
  
  @media (max-width: 480px) {
    .tech-stack {
      grid-template-columns: repeat(2, 1fr);
      gap: 0.75rem;
    }
  }

  .profile {
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .profile-pic {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    object-fit: cover;
  }

  .profile-info {
    display: flex;
    flex-direction: column;
  }

  .profile-name {
    margin: 0;
    font-size: 0.95rem;
    font-weight: 600;
    color: #f8fafc;
  }

  .profile-title {
    margin: 0;
    font-size: 0.75rem;
    color: #94a3b8;
  }

  .loading {
      font-size: 1.5rem;
      color: #f8fafc;
      text-align: center;
      margin-top: 50px;
  }

  .fade-in {
      opacity: 0;
      transform: translateY(20px);
      animation: fadeIn 0.5s forwards;
  }

  @keyframes fadeIn {
      to {
          opacity: 1;
          transform: translateY(0);
      }
  }

  .project-text {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    text-align: left;
  }

  .project-description {
    font-size: 0.75rem;
    color: #94a3b8;
  }
  .project-name {
    font-size: 1.125rem;
    font-weight: bold;
  }
  .button-svelte {
    background-color: #41322e;
  }
  .button-html {
    background-color: #412e2e;
  }
  .button-git {
    background-color: #41322e;
  }
  .button-csharp {
    background-color: #3c2e41;
  }
  .button-css {
    background-color: #2e3c41;
  }
  .button-python {
    background-color: #35412e;
  }
  .button-js {
    background-color: #41402e;
  }
  .button-swift {
    background-color: #3d3533;
  }

  .mobile-header {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    height: 60px;
    background-color: rgba(23, 23, 23, 0.8);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(38, 38, 38, 0.5);
    padding: 0 1rem;
    z-index: 100;
    align-items: center;
    justify-content: space-between;
    box-sizing: border-box;
  }

  .mobile-profile {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .mobile-name {
    font-weight: 600;
    font-size: 1rem;
  }

  .menu-toggle {
    background: none;
    border: none;
    color: #e2e8f0;
    cursor: pointer;
    padding: 0.5rem;
    border-radius: 0.375rem;
  }

  .menu-toggle:hover {
    background-color: #262626;
  }

  .mobile-nav {
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    background-color: rgba(23, 23, 23, 0.95);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border-bottom: 1px solid #262626;
    z-index: 99;
    padding: 1rem;
    transform: translateY(-150%);
    transition: transform 0.3s ease;
    visibility: hidden;
  }

  .mobile-nav-open {
    transform: translateY(0);
    visibility: visible;
  }

  .mobile-nav-links {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .project-item {
    background-color: #262626;
    color: #e2e8f0;
    padding: 0.25rem;
    border-radius: 0.375rem;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: transform 0.3s ease, background-color 0.3s ease;
    min-width: 170px;
    height: 50px;
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
  }

  .project-item:hover {
    transform: translateY(-2.15px);
  }

  .project-item:active {
    transform: scale(0.9);
  }

  .project-icon {
    width: 30px;
    height: 30px;
    padding: 10px;
  }

  .project-text {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .project-name {
    font-size: 1.125rem;
    font-weight: bold;
  }

  .project-description {
    font-size: 0.75rem;
    color: #94a3b8;
  }
</style>