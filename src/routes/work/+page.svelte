<script>
  import WorkCard from '../../components/WorkCard.svelte'; 

  const experiences = [
    {
      logo: 'visa.png',
      title: 'Software Engineer Intern',
      company: 'Visa',
      dates: 'Jun - Aug 2025',
      link: 'https://usa.visa.com/',
      description: null
    },
    {
      logo: 'uw.png',
      title: 'Research Assistant',
      company: 'Sensor Systems Lab @ UW',
      dates: 'Jun 2024 - Present',
      link: 'https://sensor.cs.washington.edu/',
      description: null
    },
    {
      logo: 'quadrant.png',
      title: 'Software Engineer Intern',
      company: 'Quadrant Technologies',
      dates: 'Jun - Aug 2023',
      link: 'https://www.quadranttechnologies.com/',
      description: null
    }
  ];
</script>

<div id="work">
  <div class="work-section-wrapper">
    <WorkCard experiences={experiences} title={"Work & Experience"}/>
  </div>
</div>
