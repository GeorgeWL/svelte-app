<script>
  export let segment;
</script>

<style>
  nav {
    font-weight: 300;
    width: 12vw;
    padding: 0 0;
    height: 100vh;
    border-bottom: 1px solid var(--primary-color);
    border-right: 1px solid var(--primary-color);
    text-transform: capitalize;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  ul {
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    padding: 0 1em;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
  }

  [aria-current]::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color:var(--primary-color);
    display: block;
    bottom: -1px;
  }
  .nav-link {
    position: relative;
    display: inline-block;
    width: fit-content;
    flex: 0 0 auto;
    border-bottom: none;
  }

  .nav-link:hover::after,
  .nav-link:focus::after {
    position: absolute;
    content: "";
    height: 2px;
    background-color: var(--primary-color);
    display: block;
    width: calc(100% - 1em);
    bottom: -1px;
    transition: transform 0.4s, opacity 0.4s;
    animation: opacityShift 3s ease forwards;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: flex;
    align-items: center;
  }
  ul.social {
    flex-direction: row;
    margin-bottom: 2px;
    background: var(--primary-color);
  }
  @media (min-width: 768px) {
    nav {
      min-width: 242px;
      border-bottom: none;
    }
  }
  @media (max-width: 768px) {
    nav {
      width: auto;
      height: auto;
      flex-direction: row;
      flex: 1 1 auto;
      border-right: none;
    }
    ul {
      flex-direction: row;
      flex: 1 1 auto;
      border-right: none;
    }
  }
  @media (max-width: 550px) {
    nav {
      flex-direction: column;
      flex: 1 1 auto;
      border-right: none;
      max-width: 95rem;
    }
    ul {
      flex-direction: row;
      flex: 1 1 auto;
      border-right: none;
    }
  }
  @media (max-width: 250px) {
    nav {
      width: calc(100% - 2em);
    }
  }
  .icon {
    display: inline-block;
    position: relative;
    height: 16px;
    top: 4px;
    margin: 0;
    padding: 0;
  }
 
  @keyframes opacityShift {
    0% {
      opacity: 0;
      filter: contrast(0.5);
    }

    90% {
      opacity: 1;
    }
  }
</style>

<nav>
  <ul class="links">
    <li>
      <a
        aria-current={segment === undefined ? 'page' : undefined}
        class="nav-link"
        href=".">home</a>
    </li>
    <li>
      <a
        aria-current={segment === 'about' ? 'page' : undefined}
        class="nav-link"
        href="about">about</a>
    </li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li>
      <a 
      rel=prefetch
       aria-current="{segment === 'blog' ? 'page' : undefined}"
        href="blog"
         class="nav-link"
>
blog
</a>
</li>
    <li>
      <a
        aria-current={segment === 'contact' ? 'page' : undefined}
        class="nav-link"
        href="contact">contact</a>
    </li>
  </ul>
  <ul class="social">
    <li>
      <a
        href="https://github.com/georgewl"
        target="_blank"
        rel="nofollow noopener"
        title="GitHub"
       >
        <img src="github.png" alt="GitHub" title="GitHub" class="icon" />
      </a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/georgewlangham/"
        target="_blank"
        rel="nofollow noopener"
        title="LinkedIn"
        >
        <img src="linkedin.png" alt="LinkedIn" title="LinkedIn" class="icon" />
      </a>
    </li>
    <li>
      <a
        href="mailto:hello@georgewl.dev?subject=Get in touch"
        target="_blank"
        rel="nofollow noopener"
        style="text-transform:none"
        title="hello@georgewl.dev">
        <img
          class="icon"
          src="email.svg"
          alt="e-mail"
          aria-hidden="true"
          title="hello@georgewl.dev" />
      </a>
    </li>
  </ul>
</nav>
