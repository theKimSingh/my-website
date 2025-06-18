<script>
  import { onMount } from 'svelte';

  export let image;
  export let name;
  export let title;
  export let description;

</script>

<div class="profile-card">
  <img src={image} alt={name} class="profile-image" />
  <div class="profile-text">
    <h1 class="profile-name">{name}</h1>
    <h2 class="profile-title">{title}</h2>
    <p class="profile-description">
      {description}
    </p>
    <div class="signature-container">
      <svg class="signature-line" viewBox="0 0 818 15" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1412.29 72.17c-11.04-5.78-20.07-14.33-85.46-25.24-22.37-3.63-44.69-7.56-67.07-11.04-167.11-22.06-181.65-21.24-304.94-30.56C888.78 1.39 822.57 1.1 756.44 0c-46.63-.11-93.27 1.56-139.89 2.5C365.5 13.55 452.86 7.68 277.94 23.15 202.57 33.32 127.38 45.01 52.07 55.69c-11.23 2.41-22.63 4.17-33.71 7.22C6.1 66.33 5.64 66.19 3.89 67.79c-7.99 5.78-2.98 20.14 8.72 17.5 33.99-9.47 32.28-8.57 178.06-29.66 4.26 4.48 7.29 3.38 18.42 3.11 13.19-.32 26.38-.53 39.56-1.12 53.51-3.81 106.88-9.62 160.36-13.95 18.41-1.3 36.8-3.12 55.21-4.7 23.21-1.16 46.43-2.29 69.65-3.4 120.28-2.16 85.46-3.13 234.65-1.52 23.42.99 1.57-.18 125.72 6.9 96.61 8.88 200.92 27.94 295.42 46.12 40.87 7.91 116.67 23.2 156.31 36.78 3.81 1.05 8.28-.27 10.51-3.58 3.17-3.72 2.66-9.7-.78-13.13-3.25-3.12-8.14-3.44-12.18-5.08-17.89-5.85-44.19-12.09-63.67-16.56l26.16 3.28c23.02 3.13 46.28 3.92 69.34 6.75 10.8.96 25.43 1.81 34.34-4.39 2.26-1.54 4.86-2.75 6.21-5.27 2.76-4.59 1.13-11.06-3.59-13.68ZM925.4 23.77c37.64 1.4 153.99 10.85 196.64 14.94 45.95 5.51 91.89 11.03 137.76 17.19 24.25 4.77 74.13 11.21 101.72 18.14-11.87-1.15-23.77-1.97-35.65-3.06-133.46-15.9-266.8-33.02-400.47-47.21Z" stroke="var(--accent-color)" stroke-width="4" stroke-linecap="round" />
      </svg>
    </div>
  </div>
</div>

<style>
  .profile-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 25px;
  }

  .profile-image {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid #333;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
  }

  .profile-name {
    font-size: 2.8em;
    font-weight: 700;
    margin: 0;
    color: var(--text-light);
  }

  .profile-title {
    font-size: 1.6em;
    font-weight: 500;
    margin: 5px 0 0;
    color: var(--text-light);
    opacity: 0.9;
  }

  .profile-description {
    font-size: 1.1em;
    color: var(--text-gray);
    margin: 15px 0 0;
    line-height: 1.6;
    max-width: 450px;
  }

  .signature-container {
    width: 100%;
    max-width: 200px;
    display: block;
    justify-content: center;
  }

  .signature-line {
    width: 100%;
    overflow: visible;
    fill: none;
  }

  .signature-line path {
    fill: var(--accent-color); /* or remove this if you want it filled */
    stroke: var(--accent-color);
    clip-path: inset(0 100% 0 0);
    animation: revealClip 2s forwards ease-out;
  }
  @keyframes revealClip {
    to {
      clip-path: inset(0 0 0 0);
    }
  } 


  @media (min-width: 769px) {
    .profile-card {
      text-align: left;
      align-items: flex-start;
      flex-direction: row;
      gap: 40px;
    }

    .profile-text {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .profile-name {
      font-size: 3.5em;
    }

    .profile-title {
      font-size: 2em;
    }

    .signature-container {
      justify-content: flex-start;
    }
  }

  @media (max-width: 480px) {
    .profile-image {
      width: 150px;
      height: 150px;
    }
    .profile-name {
      font-size: 2.2em;
    }
    .profile-title {
      font-size: 1.4em;
    }
    .profile-description {
      font-size: 1em;
    }
  }
</style>