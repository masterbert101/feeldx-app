<script>
  let navs = [
    {
      label: "Studio",
      href: "https://www.feeldx.com/studio",
    },
    {
      label: "Project Control",
      href: "https://www.feeldx.com/project-control",
    },
    {
      label: "Services",
      href: "https://www.feeldx.com/services",
    },
    {
      label: "Technology",
      href: "https://www.feeldx.com/technology",
    },
    {
      label: "Our Work",
      href: "https://www.feeldx.com/our-work",
    },
    {
      label: "Contact Us",
      href: "https://www.feeldx.com/contact-us",
    },
  ];
</script>

<div class="header">
  <a class="brand" href="/" aria-label="FeelDX">
    <svg
      width="164"
      height="42"
      viewBox="0 0 164 42"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M26.168 42H47.3525V37.0649H31.1528V25.9612H47.3525V21.0261H31.1528V9.92186H47.3525V4.98732H26.168V42Z"
        fill="#101010"
      ></path>
      <path
        d="M0 42H4.9848V25.9612H21.1834V21.0261H4.9848V9.92186H21.1834V4.98732H0V42Z"
        fill="#101010"
      ></path>
      <path
        d="M149.474 22.333L161.831 4.99901H155.729L146.423 18.0535L137.117 4.99901H131.015L143.372 22.333L129.361 41.9883H135.462L146.423 26.6124L157.384 41.9883H163.486L149.474 22.333Z"
        fill="#101010"
      ></path>
      <path
        d="M71.5475 21.0261H62.3047V25.9612H73.6128L83.107 16.5605V16.5577L83.6728 15.9982V-1.52588e-05H78.688V13.9574L71.5475 21.0261Z"
        fill="#101010"
      ></path>
      <path
        d="M83.6728 25.0972L78.688 30.0323V30.039L71.5913 37.0649H57.4125V9.92186H73.6129V4.98732H52.4277V42H73.6129V41.9572L73.6555 42L78.6936 37.0127H99.872V32.0776H83.6728V25.0972Z"
        fill="#101010"
      ></path>
      <path
        d="M116.285 4.99899V4.98732H103.826V32.0776H108.812V9.92241H116.285V9.93409C119.838 10.0532 123.204 11.534 125.674 14.0639C128.145 16.5938 129.525 19.9749 129.525 23.4937C129.525 27.0124 128.145 30.3935 125.674 32.9234C123.204 35.4533 119.838 36.9341 116.285 37.0532V37.0649H108.81V37.0104H103.826V41.9978H116.285V41.9861C121.146 41.8465 125.76 39.8368 129.149 36.3836C132.537 32.9304 134.432 28.3057 134.432 23.4914C134.432 18.6772 132.537 14.0525 129.149 10.5993C125.76 7.1461 121.146 5.13635 116.285 4.99676V4.99899Z"
        fill="#101010"
      ></path>
    </svg>
  </a>

  <nav class="desktop-nav">
    <ul class="primary">
      {#each navs as nav}
        <li class="menu-item">
          <a class="item" href={nav.href}> {nav.label} </a>
        </li>
      {/each}
    </ul>
  </nav>

  <div class="mobile-nav">
    <input type="checkbox" id="burger-toggle" />
    <label for="burger-toggle" class="burger-container">
      <div class="burger-line"></div>
      <div class="burger-line"></div>
      <div class="burger-line"></div>
    </label>
    <nav class="nav-menu">
      <ul>
        <li>
          <a class="" href="https://www.feeldx.com/studio">Studio</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/project-control"
            >Project Control</a
          >
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/services">Services</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/technology">Technology</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/our-work">Our Work</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/contact-us">Contact Us</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/about-us">About Us</a>
        </li>

        <li>
          <a class="" href="https://www.feeldx.com/news">News</a>
        </li>

        <li>
          <a class="" href="tel:1800333539">1800 333 539</a>
        </li>
      </ul>
    </nav>
  </div>
</div>

<style lang="scss">
  .header {
    position: absolute;
    width: -webkit-fill-available;
    z-index: 999;
    opacity: 1;
    transition: all 0.25s ease-in-out;
    animation: fade-in 2.5s forwards;

    display: flex;
    justify-content: space-between;
    align-items: center;
    min-height: 90px;
    padding: 1rem 2rem 0;
    color: #2a2f1e;
  }

  .desktop-nav {
    display: none;

    @media only screen and (min-width: 640px) {
      width: 100%;
      display: flex;
      flex: 1;
      gap: 2rem;
      align-items: center;
      font-weight: 400;
      font-size: 0.8rem;
    }
  }

  ul li {
    list-style: none;
  }

  .primary {
    background-color: #f8f5ee;
    border-radius: 30px;
    padding: 0.85rem;
    display: flex;
    margin-inline: auto;
    gap: 0.5rem;
    width: fit-content;
    align-items: center;
    justify-content: space-evenly;
    position: relative;
  }

  .item {
    text-decoration: none;
    color: #2a2f1e;
    text-transform: uppercase;
    font-size: 1rem;
    font-weight: 600;
    padding: 0.5rem 1rem;
    border-radius: 30px;
    transition: background-color 0.3s ease;

    &:hover {
      background-color: #e2ded6;
    }
  }

  .mobile-nav {
    @media (min-width: 768px) {
      display: none;
    }

    @media (min-width: 922px) {
      .nav-menu {
        width: 970px;
      }
    }

    @media (min-width: 1200px) {
      .nav-menu {
        width: 1170px;
      }
    }

    .burger-container {
      position: fixed;
      top: 40px;
      right: 20px;
      z-index: 1000;
      cursor: pointer;
      width: 40px;
      height: 30px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 5px;
      border-radius: 5px;
      background: transparent;
    }

    .burger-line {
      width: 100%;
      height: 3px;
      background-color: #2a2f1e;
      border-radius: 2px;
      transform-origin: center;
      transition: all 0.4s ease-in-out;
    }

    #burger-toggle {
      display: none;
    }

    /* Navigation Styles */
    .nav-menu {
      position: fixed;
      top: 0;
      right: -300px;
      width: 300px;
      height: 100%;
      background: linear-gradient(135deg, #2a2f1e 0%, #273849 100%);
      transition: right 0.4s cubic-bezier(0.77, 0.2, 0.05, 1);
      box-shadow: -4px 0 15px #00000033;
      overflow-y: auto;
      padding-top: 100px;
    }

    .nav-menu::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 80px;
      background: #ffffff0d;
      backdrop-filter: blur(10px);
    }

    .nav-menu ul {
      list-style-type: none;
    }

    .nav-menu ul li {
      margin: 0 15px;
      border-bottom: 1px solid #ffffff1a;
    }

    .nav-menu ul li a {
      color: white;
      text-decoration: none;
      display: block;
      padding: 15px;
      font-weight: 500;
      position: relative;
      overflow: hidden;
    }

    .nav-menu ul li a::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: -100%;
      width: 100%;
      height: 2px;
      background-color: var(--secondary-color);
      transition: left 0.3s ease;
    }

    .nav-menu ul li a:hover::after {
      left: 0;
    }

    /* Burger Icon Animation on Checkbox Checked */
    #burger-toggle:checked ~ .burger-container .burger-line:nth-child(1) {
      transform: rotate(45deg) translate(14px, 5px);

      background-color: #fff;
    }

    #burger-toggle:checked ~ .burger-container .burger-line:nth-child(2) {
      opacity: 0;
    }

    #burger-toggle:checked ~ .burger-container .burger-line:nth-child(3) {
      transform: rotate(-45deg) translate(14px, -5px);
      background-color: #fff;
    }

    /* Navigation Slide In */
    #burger-toggle:checked ~ .nav-menu {
      right: 0;
    }
  }
</style>
