<div class="layout">
  <aside class="sidebar">
    <nav class="nav-links">
      <a href="/" class="nav-link">Home</a>
      <a href="/about" class="nav-link">About</a>
      <a href="https://github.com/Ondraaasek" class="nav-link">Github</a>
      <a href="https://discord.com/users/yan5q" class="nav-link">Discord</a>
      <a href="mailto:yan5q@yan5q.org" class="nav-link">Email</a>
      <a href="https://matrix.to/#/@yan5q:matrix.org" class="nav-link">Matrix</a>
    </nav>
  </aside>

  <main class="container">
    <section class="intro">
      <p class="location">Prague, Czech Republic</p>
      <h1>Hey, I'm yan5q</h1>
      <p class="intro-text">
        I'm a cybersecurity student from Czech Republic, who likes learning new stuff, 
        coding, traveling, I'm currently learning C#.
      </p>
    </section>

    <section class="content">
      <div class="section">
        <h2>My technologies</h2>
        <div class="tech-stack">
          <span class="tech-item">C#</span>
          <span class="tech-item">Svelte</span>
          <span class="tech-item">HTML</span>
          <span class="tech-item">CSS</span>
          <span class="tech-item">JavaScript</span>
          <span class="tech-item">JSON</span>
          <span class="tech-item">Python</span>
          <span class="tech-item">Swift</span>
        </div>
      </div>
      
      <div class="section">
        <h2>My projects</h2>
        <ul class="projects-list">
          <li><strong>yan5q.org</strong> - my personal site (Svelte, CSS, JavaScript)</li>
          <li><strong>AutoCertificate</strong> - for preparation courses for applicants (python)</li>
          <li><strong>SSPSliminal</strong> - unfinished liminal game (Unity)</li>
        </ul>
      </div>
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
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
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
    gap: 0.75rem;
  }

  .nav-link {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.875rem;
    padding: 0.5rem;
    border-radius: 0.375rem;
    transition: all 0.2s ease;
  }

  .nav-link:hover {
    color: #e2e8f0;
    background-color: #262626;
  }

  .container {
    flex: 1;
    max-width: 640px;
    padding: 6rem 1.5rem;
    margin: 0 auto;
    margin-left: calc(16rem + 4rem); /* sidebar width + some spacing */
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
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .tech-item {
    background-color: #262626;
    color: #e2e8f0;
    padding: 0.25rem 0.75rem;
    border-radius: 0.375rem;
    font-size: 0.875rem;
  }

  .projects-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .projects-list li {
    color: #94a3b8;
    line-height: 1.75;
  }

  .projects-list strong {
    color: #e2e8f0;
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
</style>