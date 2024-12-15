<script>
    import { onMount } from 'svelte';
    import { page } from '$app/stores';
    import { Home, User, Github, MessageSquare, Mail, MessageCircle, MapPin } from 'lucide-svelte';
  
    $: currentPath = $page.url.pathname;

    let activeLink = '';

    function handleClick(link) {
        activeLink = link;
        setTimeout(() => {
            activeLink = '';
        }, 300); // Duration of the scale effect
    }

    // Example of using onMount to safely access DOM elements
    onMount(() => {
      // Any DOM-related code can go here
      console.log('About page mounted');
    });
</script>
  
  <div class="layout">
    <aside class="sidebar">
      <div class="profile">
        <img src="https://motionbgs.com/media/3335/topographic-textures.jpg" alt="Topographic pattern avatar" style="width: 40px; height: 40px; border-radius: 50%; object-fit: cover; border: 1px solid #fff; box-shadow: 0 0 10px rgba(0,0,0,0.1);">
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
        <h1 class="fade-in">About Me</h1>
        <p class="intro-text fade-in">
          I'm a cybersecurity student passionate about technology and coding. 
          Currently focusing on learning C# and exploring various aspects of software development.
        </p>
      </section>
  
      <section class="content fade-in">
        <h2 class="fade-in">My Interests</h2>
        <ul class="interests-list fade-in">
          <li class="fade-in">Software Development</li>
          <li class="fade-in">Cybersecurity</li>
          <li class="fade-in">Open Source Projects</li>
          <li class="fade-in">Learning New Technologies</li>
        </ul>
      </section>
  
      <footer>
        <hr>
        <h3>yan5q</h3>
        <p>Student and Developer - 2024</p>
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
      transition: all 0.2s ease;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      position: relative;
    }
  
    .nav-link:hover {
      color: #f8fafc;
      background-color: #262626;
    }
  
    .nav-link.active {
      color: #f8fafc;
      background-color: #262626;
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
    }
  
    .container {
      flex: 1;
      max-width: 640px;
      padding: 6rem 1.5rem;
      margin: 0 auto;
      margin-left: calc(16rem + 4rem);
    }
  
    .location {
      color: #94a3b8;
      font-size: 0.875rem;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.375rem;
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
  
    .about-list {
      list-style: none;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      color: #94a3b8;
    }
  
    .about-list strong {
      color: #e2e8f0;
      display: block;
      margin-bottom: 0.25rem;
    }
  
    .about-list p {
      margin: 0;
      font-size: 0.875rem;
    }
  
    .focus-text {
      color: #94a3b8;
      line-height: 1.75;
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
  
      .container {
        margin-left: 0;
        padding: 4rem 1rem;
      }
  
      h1 {
        font-size: 2rem;
      }
  
      .intro-text {
        font-size: 1rem;
      }
    }
  
    .nav-link {
      transition: transform 0.3s ease;
    }
  
    .nav-link:active {
      transform: scale(0.9);
    }
  
    .nav-link.active {
      color: #f8fafc;
      background-color: #262626;
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
  </style>