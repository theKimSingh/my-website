<script>
  export let experiences;
  export let title;
</script>

<section class="work-experience">
  <div class="header">
    <button
        type="button"
        aria-label="Go back"
        on:click={() => window.history.back()}
        class="back-button">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="feather feather-arrow-left"
          aria-hidden="true"
          focusable="false"
        >
          <line x1="19" y1="12" x2="5" y2="12"></line>
          <polyline points="12 19 5 12 12 5"></polyline>
        </svg>
      </button>
    <h2>{title}</h2>
  </div>
  <div class="experience-list">
    {#each experiences as exp}
      <div class="experience-item">
        <div class="header"></div>
        <div class="logo-container">
          {#if exp.logo}
            <img src="logos/{exp.logo}" alt="{exp.company} Logo" class="company-logo" />
          {/if}
        </div>
        <div class="details-container">
          <h3 class="job-title">{exp.title}</h3>
          <p class="company-name">{exp.company}</p>
          {#if exp.description}
            <p class="job-description">{exp.description}</p>
          {/if}
        </div>
        <div class="dates-container">
          <p class="job-dates">{exp.dates}</p>
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  .header {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .work-experience h2 {
    position: relative;
    display: inline-block;
    overflow: visible;
  }

  .work-experience h2::after {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    bottom: -6px;
    width: 100%;
    height: 3px;
    background: var(--accent-color);
    border-radius: 2px;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s cubic-bezier(.4,1,.4,1);
  }

  .work-experience h2:hover::after  {
    transform: scaleX(1);
  }

  .back-button {
    all: unset;
    box-sizing: border-box;
    display: inline;
    line-height: 1;
    vertical-align: middle;

  }

  .back-button svg {
    color: white;
    width: 32px;
    height: 32px;
  }

  .back-button svg:hover {
    color: var(--icon-accent);
    transform: scale(1.2);
    transition:
      transform 0.2s ease-in-out,
      color 0.5s ease-out;
  }


  .work-experience {
    width: 100%;
    max-width: 700px;
    box-sizing: border-box;
  }

  h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: var(--text-light);
    margin-bottom: 30px;
    text-align: left;
  }

  .experience-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .experience-item {
    display: flex;
    align-items: flex-start;
    background-color: #2b333b;
    padding: 20px;
    border-radius: 8px;
    border-bottom: 2px solid #2b333b;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    transition:
      transform 0.2s ease-in-out,
      border-bottom-color 0.2s ease-out;
  }

  .experience-item:hover {
    transform: translateY(-5px);
    border-bottom-color: var(--accent-color);
  }

  .logo-container {
    flex-shrink: 0; 
    width: 50px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 20px;
    border-radius: 8px;
    background-color: white;
  }

  .company-logo {
    width: 40px;
    height: 40px;
    object-fit: contain;
    border-radius: 4px;
  }


  .job-title {
    font-size: 1.2em;
    font-weight: 600;
    color: var(--text-light);
    margin: 0 0 5px 0;
  }

  .company-name {
    font-size: 0.95em;
    color: var(--text-gray);
    margin: 0;
  }

  .job-description {
    font-size: 0.9em;
    color: var(--text-gray);
    margin: 10px 0 0 0;
    line-height: 1.5;
  }

  .dates-container {
    flex-shrink: 0;
    margin-left: 20px;
    text-align: right;
  }

  .job-dates {
    font-size: 0.95em;
    color: var(--text-gray);
    margin: 0;
    white-space: nowrap;
  }

  /* Responsive adjustments */
  @media (max-width: 600px) {
    .experience-item {
      flex-direction: column;
      align-items: flex-start;
      padding: 15px;
    }



    .logo-container {
      margin-right: 0;
      margin-bottom: 10px;
    }

    .dates-container {
      width: 100%;
      text-align: left;
      margin-left: 0;
      margin-top: 10px;
    }
    /* .work-experience {
      width: 500px;
    } */
  }

  @media (max-width: 400px) {
    .work-experience {
      padding: 0 10px;
    }
  }
</style>