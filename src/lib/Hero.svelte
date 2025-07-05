<script>
</script>

<section class="container">
  <video
    class="video"
    autoplay
    loop
    muted
    playsinline
    width="1920"
    height="1280"
  >
    <source src="/herovid.webm" type="video/webm" />
  </video>

  <div class="bg-gradient"></div>

  <div class="content-container">
    <header>
      <h1>
        Plan.
        <br />
        Visualise.
        <br />
        Transform.
      </h1>
      <p>
        We push beyond visual representation, integrating and connecting with
        your project's requirements, bringing them to life and enhancing clarity
        to create a truly immersive experience.
      </p>
      <a class="hero-cta" href="https://www.feeldx.com/our-work">
        <span> View Our Work </span>
        <svg
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M4 12H20M20 12L14 6M20 12L14 18"
            stroke="#ffffff"
            stroke-width="2.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </a>
    </header>
  </div>
</section>

<style lang="scss">
  .container {
    position: relative;
    height: calc(100vh - 10px);
    overflow: hidden;
  }

  .bg-gradient {
    bottom: 0;
    top: unset;
    background: linear-gradient(
      180deg,
      rgba(255, 254, 254, 0) 0%,
      rgb(255, 255, 255) 100%
    );
    z-index: 1;

    content: "";
    position: absolute;
    height: 50%;
    width: 100%;
    pointer-events: none;
  }

  .video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    margin: 0;
  }

  .content-container {
    position: absolute;
    bottom: 2rem;
    display: grid;
    align-items: center;
    gap: 0.5rem;
    padding: 0 2rem;
    z-index: 2;

    h1 {
      margin: 0;
      color: #2a2f1e;
      font-size: 4rem;
      font-weight: 600;
      line-height: 1.1;

      @media only screen and (min-width: 640px) {
        font-size: 5.75rem;

        font-weight: 600;
        line-height: 1.1;
      }
    }

    p {
      margin: 1rem 0;
      font-size: 1rem;
      color: #2a2f1e;
      font-weight: 400;
      max-width: 500px;
    }
  }

  .hero-cta {
    padding: 1rem 2rem;
    background-color: #2a2f1e;
    border-radius: 9999px;

    text-decoration: none;

    span {
      color: #fff;
      font-size: 1rem;
      font-weight: 700;
      text-transform: uppercase;
    }

    display: inline-flex;
    align-items: center;
    gap: 0.65rem;

    &:hover {
      svg {
        transform: translateX(9px);
        transition: transform 0.25s ease-in-out;
      }
    }
  }
</style>
