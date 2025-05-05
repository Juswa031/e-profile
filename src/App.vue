<template>
  <div class="d-flex justify-content-start flex-wrap gap-3 align-items-center animate__animated animate__fadeIn">
    <div class="col-12 col-md-auto text-center text-md-start">
      <img src="./assets/images/profile-new.JPG" alt="Image" class="img-fluid rounded" width="130" height="130"/>
    </div>
    
    <div class="col text-center text-md-start">
      <h4 class="mb-1 fw-bold">Joshua Sandoval</h4>
      <h6 class="mb-0">Software Engineer</h6>
      <div class="mt-1 gap-1 align-items-center d-md-flex">
        <i class="bi bi-geo-alt me-1"></i>
        <h7 class="mb-0">Pasig City</h7>
      </div>
      <div class="mt-1 gap-1 align-items-center d-md-flex">
        <i class="bi bi-envelope me-1"></i>
        <h7 class="mb-0">joshua.sandoval031@gmail.com</h7>
      </div>
      <div class="mt-1 gap-1 align-items-center d-md-flex">
        <i class="bi bi-telephone"></i>
        <h7 class="mb-0">+639171353922</h7>
      </div>
    </div>
    <div class="col-12 col-md-auto text-center text-md-end" @click="toggleTheme()">
      <label
        for="themeToggle"
        class="themeToggle st-sunMoonThemeToggleBtn"
        type="checkbox"
      >
        <input type="checkbox" id="themeToggle" class="themeToggleInput" />
        <svg
          width="18"
          height="18"
          viewBox="0 0 20 20"
          fill="currentColor"
          stroke="none"
        >
          <mask id="moon-mask">
            <rect x="0" y="0" width="20" height="20" fill="white"></rect>
            <circle cx="11" cy="3" r="8" fill="black"></circle>
          </mask>
          <circle
            class="sunMoon"
            cx="10"
            cy="10"
            r="8"
            mask="url(#moon-mask)"
          ></circle>
          <g>
            <circle class="sunRay sunRay1" cx="18" cy="10" r="1.5"></circle>
            <circle class="sunRay sunRay2" cx="14" cy="16.928" r="1.5"></circle>
            <circle class="sunRay sunRay3" cx="6" cy="16.928" r="1.5"></circle>
            <circle class="sunRay sunRay4" cx="2" cy="10" r="1.5"></circle>
            <circle class="sunRay sunRay5" cx="6" cy="3.1718" r="1.5"></circle>
            <circle class="sunRay sunRay6" cx="14" cy="3.1718" r="1.5"></circle>
          </g>
        </svg>
      </label>

    </div>

    <!-- About and Experience -->
    <div class="col-12 mt-4">
      <div class="d-flex justify-content-start flex-wrap gap-3">
          <div class="col-12 col-lg-8">
            <div class="d-flex justify-content-start flex-wrap gap-3">
              <div class="col-12 border rounded p-3">
                <div class="d-flex gap-2 align-items-center fs-5">
                    <i class="bi bi-person-vcard"></i>
                    <span class="mb-0 fw-bold">About</span>
                  </div>
                  <p class="mt-2">
                    I am an experienced Full Stack Developer with a solid foundation in creating innovative, scalable web applications. I have hands-on experience of both front-end and back-end technologies, and my fields of expertise are developing effective databases, reliable APIs, and responsive user interfaces.
                  </p>
                  <p class="mt-2 mb-0">
                    Being able to quickly adapt to new challenges and provide customized solutions derives from my experience working as a freelancer on a range of projects over the years, I'm passionate about user experience, speed optimization, and clean code, and I work hard to apply both technical expertise and innovative problem-solving to every project.
                  </p>
              </div>
              <div class="col-12 border rounded p-3">
                <div class="d-flex gap-2 align-items-center fs-5">
                  <i class="bi bi-laptop"></i>
                  <span class="mb-0 fw-bold">Tech Stacks</span>
                </div>

                <template v-for="(tech_stack, index) in tech_stacks" :key="index">
                  <div class="fs-7 mt-3 fw-bold">{{ tech_stack.title }}</div>
                  <div class="d-flex gap-2 flex-wrap mt-1">
                    <span class="badge bg-secondary" v-for="(tech, index) in tech_stack.technologies" :key="index">{{ tech }}</span>
                  </div>
                </template>
              </div>
            </div>
          </div>

          <div class="col border rounded p-4 shadow-sm">
            <div class="d-flex gap-2 align-items-center fs-5 mb-3">
              <i class="bi bi-briefcase-fill"></i>
              <span class="fw-bold">Experience</span>
            </div>

            <div class="mb-3">
              <div class="d-flex justify-content-between flex-wrap">
                <div>
                  <h6 class="mb-1 fw-semibold">Full Stack Software Engineer</h6>
                </div>
                <div class="small">October 2024 – Present</div>
              </div>
              <div class="small">Integratr · Hybrid</div>
              <p class="mt-2 mb-1 small text-secondary">
                Spearheaded the development of responsive web apps using Vue.js, Laravel, and PostgreSQL. Led deployment pipelines and performance optimization for client projects.
              </p>
            </div>

            <div class="mb-3">
              <div class="d-flex justify-content-between flex-wrap">
                <div>
                  <h6 class="mb-1 fw-semibold">Associate Software Engineer</h6>
                </div>
                <div class="small">September 2022 – October 2024</div>
              </div>
              <div class="small">Integratr · Hybrid</div>
              <p class="mt-2 mb-1 small text-secondary">
                Collaborated on internal tools and enterprise solutions, contributing to backend API development and frontend enhancements in a fast-paced Agile environment.
              </p>
            </div>
          </div>
      </div>
    </div>

    <div class="col-12 border rounded p-3">
        <div class="d-flex gap-2 align-items-center fs-5">
          <i class="bi bi-laptop"></i>
          <span class="mb-0 fw-bold">Projects</span>
        </div>

        <div class="mt-3 scrollable-projects">
          <div class="mb-4" v-for="(project, index) in projects" :key="index">
            <h6 class="fw-semibold mb-0">{{ project.title }}</h6>
            <span class="small mb-2">{{ project.type }}</span>
            <div class="small">{{ project.technologies.join(' · ') }}</div>
            <p class="small text-secondary mt-1">
              {{ project.description }}
            </p>
          </div>
        </div>
    </div>
  </div>

  <hr class="my-5">
  © 2025 Joshua. All rights reserved.
</template> 

<script>
export default {
  name: 'App',
  data() {
    return {
      tech_stacks: [
        {
          title: 'Frontend',
          technologies: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'TypeScript'],
        },
        {
          title: 'Backend',
          technologies: ['Node.js', 'PHP', 'Laravel', 'MySQL', 'PostgreSQL', 'RESTApi'],
        },
        {
          title: 'DevOps & Cloud',
          technologies: ['AWS', 'GitHub Actions', 'Docker', 'Hostinger'],
        },
        {
          title: 'Developer Tools',
          technologies: ['Git', 'GitHub', 'ClickUp', 'Discord', 'Slack', 'Teams'],
        }
      ],
      projects: [
        {
          title: 'Ambiance Furniture',
          type: 'Capstone',
          description: 'Is an online store offering stylish, high-quality furniture for every room. Shop modern and classic pieces designed to elevate your home with comfort and elegance.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Click to Cart',
          type: 'Capstone',
          description: 'Is your go-to online store for the latest gadgets and tech accessories. From smart devices to innovative electronics, we offer top-quality products to enhance your digital lifestyle.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Country Wheels',
          type: 'Capstone',
          description: 'Is an online bike rental service offering quality bikes for every adventure. Rent easily and ride with freedom!',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Enrollment System',
          type: 'Capstone',
          description: 'Is an efficient online platform that simplifies the registration process. Easily manage student sign-ups, course selections, and schedules in one seamless system.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'IELS',
          type: 'Capstone',
          description: 'Is an online bakery offering fresh, handmade bread delivered straight to your door. Enjoy the finest quality loaves baked with love and delivered for your convenience.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'One Pasig',
          type: 'Capstone',
          description: 'Is an online platform that simplifies the process of applying for a business permit. Easily submit your requirements, track your application, and get your permit fast—all from the comfort of your home.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Real Property Tax',
          type: 'Capstone',
          description: 'Is an online platform that simplifies the process of purchasing land and managing property taxes. Browse available properties, complete transactions, and handle tax payments easily, all in one place.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Sytrontec Enterprise',
          type: 'Capstone',
          description: 'Is your online destination for high-quality electronic parts, offering a wide selection for all your project needs.',
          technologies: ['HTML', 'CSS', 'PHP', 'MySQL'],
        },
        {
          title: 'Momeco PH',
          description: 'Is your online destination for high-quality electronic parts, offering a wide selection for all your project needs.',
          technologies: ['Vuejs', 'Laravel', 'MySQL'],
        },
      ],
    };
  },
  methods: {
    toggleTheme() {
      const themeToggleInput = document.querySelector('.themeToggleInput');
      const sunMoon = document.querySelector('.sunMoon');
      const sunRays = document.querySelectorAll('.sunRay');

      if (themeToggleInput.checked) {
        document.body.classList.remove('dark-theme');
        sunMoon.classList.remove('dark');
        sunRays.forEach((ray) => ray.classList.remove('dark'));
      } else {
        document.body.classList.add('dark-theme');
        sunMoon.classList.add('dark');
        sunRays.forEach((ray) => ray.classList.add('dark'));
      }
    }
  },
};
</script>