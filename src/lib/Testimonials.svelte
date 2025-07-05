<script>
  let testimonials = [
    {
      name: "TIER 2 VIC",
      text: "Quality of visuals and attention to detail captured the intent of our programme and methodology.",
      title: "Estimating Manager",
    },
    {
      name: "Tier 3 - NSW & VIC",
      text: "Thank you team, just had a look – everything looks really well put together! Thanks again for being so responsive and making the process easy for us. You brought the story to life and helped portray the end vision to the client. Well done.",
      title: "National Brand & Submissions Coordinator Tender Manager",
    },
    {
      name: "Claire Lee",
      text: "Combined with their technical understanding on how to plan and build efficiently and safely, FeelDX’s visualisation team was a breeze to deal with. Quality of visuals and attention to detail captured the intent of our programme and methodology.",
      title: "Founder at StartupX",
    },
    {
      name: "Tier 3 - VIC",
      text: "The support team was amazing and super quick to respond.",
      title: "Estimating Manager Estimating Manager",
    },
    {
      name: "TIER 2 NSW",
      text: "You brought the story to life and helped portray the end vision to the client. Well done. Combined with their technical understanding on how to plan and build efficiently and safely, FeelDX’s visualisation team was a breeze to deal with.",
      title: "Tender Manager Estimating Manager",
    },
  ];

  let allTestimonials = [...testimonials, ...testimonials];

  let isHovered = $state(false);
</script>

<section class="container">
  <header class="header">
    <h2>Testimonials</h2>
    <p>
      Hear directly from our happy users who’ve experienced the difference our
      product makes. Real stories, real impact.
    </p>
  </header>

  <div
    class="slider-wrapper"
    aria-label="Testimonial slider"
    onmouseenter={() => (isHovered = true)}
    onmouseleave={() => (isHovered = false)}
    role="region"
  >
    <div class="slider" class:paused={isHovered}>
      {#each allTestimonials as t, i}
        <div class="testimonial" aria-label={`Testimonial by ${t.name}`}>
          <p>"{t.text}"</p>
          <span class="name">{t.name}</span>
          <span class="title">{t.title}</span>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .container {
    padding: 3rem 1rem;
    @media only screen and (min-width: 640px) {
      padding: 5rem 2rem;
    }
  }

  .header {
    h2 {
      font-size: 2.75rem;
      margin: 0;
      text-transform: uppercase;

      @media only screen and (min-width: 640px) {
        font-size: 3.5rem;
      }
    }
    p {
      font-size: 0.85rem;
      @media only screen and (min-width: 640px) {
        font-size: 1rem;
        max-width: 750px;
      }
    }
  }

  .slider-wrapper {
    overflow: hidden;
    width: 100%;
    padding: 1rem 0;
  }

  .slider {
    display: flex;
    width: max-content;
    animation: scroll 50s linear infinite;
    animation-play-state: running;

    mask-image: linear-gradient(
      var(left, to right),
      hsl(0 0% 0% / 0),
      hsl(0 0% 0% / 1) 10%,
      hsl(0 0% 0% / 1) 90%,
      hsl(0 0% 0% / 0)
    );
  }

  .slider.paused {
    animation-play-state: paused;
  }

  .testimonial {
    flex: 0 0 300px;
    margin-right: 2rem;
    background-color: rgba(38, 43, 30);
    padding: 1rem 1.5rem;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    user-select: none;

    @media only screen and (min-width: 640px) {
      flex: 0 0 500px;
    }
  }

  .testimonial {
    p {
      font-size: 1.15rem;
      font-style: italic;
      margin-bottom: 0.8rem;
      color: #fff;
      @media only screen and (min-width: 640px) {
        font-size: 1.45rem;
      }
    }
  }

  .testimonial {
    .name {
      display: block;
      font-size: 1rem;
      font-weight: bold;
      color: #fff;

      @media only screen and (min-width: 640px) {
        font-size: 1.15rem;
      }
    }
  }

  .testimonial {
    .title {
      font-size: 0.75rem;
      color: #fff;
      /* color: #2a2f1e; */
      @media only screen and (min-width: 640px) {
        font-size: 0.85rem;
      }
    }
  }

  @keyframes scroll {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
</style>
