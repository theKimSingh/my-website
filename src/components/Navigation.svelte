<nav class="main-nav">
  <ul>
    <li><a href="work">work</a></li>
    <li><a href="projects">projects</a></li>
    <!-- <li><a href="#resume">resume</a></li> -->
  </ul>
</nav>

<style>
  .main-nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .main-nav li a {
    font-size: 1.1em;
    font-weight: 500;
    color: var(--text-gray);
    text-transform: lowercase; /* Matches the image */
    position: relative; /* For the underline effect */
  }

  .main-nav li a::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    bottom: -5px;
    left: 0;
    background-color: var(--accent-color);
    transition: width 0.2s ease-out;
  }

  .main-nav li a:hover::after {
    width: 100%;
  }

  .main-nav li a:hover {
    color: var(--text-light); /* Make text brighter on hover */
  }

  @media (max-width: 768px) {
    .main-nav ul {
      justify-content: center; /* Center links on smaller screens */
    }
  }
</style>