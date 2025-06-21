<script>
  import ProfileCard from '../components/ProfileCard.svelte';
  import Navigation from '../components/Navigation.svelte';
  import SocialLinks from '../components/SocialLinks.svelte';
  import WorkCard from '../components/WorkCard.svelte'; 
  const profileImage = 'logo-placeholder.jpg';
</script>

<main class="portfolio-container">
  <div class="profile-section">
    <ProfileCard
      image={profileImage}
      name="Kim Singh"
      title="CS @ Univ. of Washington"
      description="Avid builder & learner. Currently exploring MCP!"
    />
  </div>
  <div class="info-section">
    <Navigation />
    <SocialLinks />
  </div>
</main>

<style>
  .portfolio-container {
    display: flex;
    align-items: center;
    border-radius: 12px;
    padding: 40px;
    max-width: 900px;
    width: 90%;
    gap: 60px;
    box-sizing: border-box;
    border-width: 1rem;
    border-color: var(--text-light);
  }

  .profile-section {
    flex-shrink: 0;
  }

  .info-section {
    display: flex;
    flex-direction: column;
    gap: 30px;
    flex-grow: 1;
  }

  /* Responsive adjustments */
  @media (max-width: 768px) {
    .portfolio-container {
      flex-direction: column;
      text-align: center;
      gap: 30px;
      padding: 30px;
    }

    .info-section {
      align-items: center;
    }
  }

  @media (max-width: 480px) {
    .portfolio-container {
      padding: 20px;
    }
  }
</style>