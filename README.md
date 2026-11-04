# Sundarbans House — IIT Madras BS Degree

A centralized community platform for **Sundarbans House** of the IIT Madras BS Degree programme. The website brings together house information, events, meetups, study resources, teams, community activities and member-facing tools in one place.

Built primarily with **Vue 3 and Vite**, the platform combines reusable components, structured data and static assets to support the Sundarbans House community.

## Overview

Sundarbans House is a student community within the IIT Madras BS Degree programme. This platform serves as its digital hub, helping members discover house activities, find academic resources, explore regional meetups, learn about teams and access member-oriented pages.

The repository also retains a legacy standalone HTML section alongside the Vue application.

## Features

### Community & House Information
- House landing page and introduction.
- About and contact pages.
- Dedicated pages for house teams and community information.
- Shared navigation and footer components.

### Events & Community Activities
- Events page for house activities.
- Separate community sections for technical, cultural and E-Sports activities.
- Event posters and supporting media organized in project assets.

### Regional Meetups
- Meetup landing page.
- Region-specific meetup pages.
- Shared region configuration.
- Meetup data organized in JSON and CSV exports.

### Study Corner
- Study and resource section for students.
- Doubt and FAQ content supported by structured data.

### Members Area
- Login and members-lounge views.
- Dashboard and member-oriented pages.
- Static member and student-council data used by the frontend.

### UI & Experience
- Vue-based multi-page navigation.
- Reusable components and shared layouts.
- Scroll and interface animation utilities.
- Responsive styling and locally managed image assets.

> **Implementation note:** The repository contains frontend pages and static data/assets. The presence of a frontend login or member page alone does not imply a production-secured backend.

## Technology Stack

| Area | Technology |
|---|---|
| Frontend framework | Vue 3 |
| Build tool | Vite |
| Language | JavaScript |
| Markup | HTML5 |
| Styling | CSS3 |
| Routing | Vue Router |
| Data | JSON and CSV |
| Assets | Images, logos, posters and animation frames |
| Version control | Git and GitHub |

## Project Structure

```text
Sundarbans-House_Vue/
├── index.html
├── vite.config.js
├── package.json
├── .env.example
├── public/
│   ├── assets/
│   │   ├── logo.png
│   │   └── frames/
│   └── data/
│       └── doubts.json
│
├── sundarbans/                  # Legacy standalone HTML pages
│   ├── login.html
│   ├── dashboard.html
│   ├── members.html
│   └── whatsapp.html
│
└── src/
    ├── main.js
    ├── App.vue
    ├── router/
    │   └── index.js
    ├── composables/
    │   └── useAnimations.js
    ├── components/
    ├── data/
    ├── assets/
    │   ├── style.css
    │   ├── regions/
    │   ├── teams/
    │   └── Community Events/
    │       ├── Cultural/
    │       ├── E-Sports/
    │       └── Technical/
    └── views/
        ├── HomeView.vue
        ├── AboutView.vue
        ├── EventsView.vue
        ├── StudyView.vue
        ├── TeamsView.vue
        ├── CommunityView.vue
        ├── ContactView.vue
        ├── LoginView.vue
        ├── MembersLoungeView.vue
        ├── DashboardView.vue
        ├── TechnicalView.vue
        ├── CulturalView.vue
        ├── ESportsView.vue
        ├── MeetupsView.vue
        └── meetups/
            ├── regionConfigs.js
            ├── DelhiMeetups.vue
            ├── MumbaiMeetups.vue
            ├── BangaloreMeetups.vue
            ├── KolkataMeetups.vue
            ├── HyderabadMeetups.vue
            ├── PatnaMeetups.vue
            ├── ChandigarhMeetups.vue
            └── region_exports_json_and_csv/
```

## Getting Started

### Prerequisites
- Node.js (LTS recommended)
- npm
- Git

### 1. Clone the repository

```bash
git clone https://github.com/Code-Samar/Sundarbans-House_Vue.git
cd Sundarbans-House_Vue
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment

Review `.env.example` and add the environment variables required by your local or deployment setup to a local `.env` file.

Do not commit real credentials, tokens or private configuration values.

### 4. Start the development server

```bash
npm run dev
```

Open the local URL printed by Vite in your terminal (commonly `http://localhost:5173`).

### 5. Create a production build

```bash
npm run build
```

### 6. Preview the production build

```bash
npm run preview
```

## Application Screenshots

<img width="100%" alt="Sundarbans House website preview" src="https://github.com/user-attachments/assets/04fef05d-a7f3-4fe1-8ef9-20a104ec3600" />

<img width="100%" alt="Sundarbans House website view" src="https://github.com/user-attachments/assets/65d285ed-e47b-4ba9-ac84-96444b8f1f2d" />

<img width="100%" alt="Sundarbans House community page" src="https://github.com/user-attachments/assets/890ea9bb-9ed4-4cb8-b451-e50d6f2c563f" />

<img width="100%" alt="Sundarbans House member interface" src="https://github.com/user-attachments/assets/bfa0416c-d0cc-4473-ba4e-94eee8d91757" />

<img width="100%" alt="Sundarbans House additional page preview" src="https://github.com/user-attachments/assets/713db9a5-2d45-4e5b-b52f-4f247284ec49" />

## Development Notes

- Reusable UI elements belong in `src/components/`.
- Page-level Vue components belong in `src/views/`.
- Route definitions are maintained in `src/router/index.js`.
- Shared animation behavior is maintained in `src/composables/useAnimations.js`.
- Update regional meetup configuration and corresponding data exports together when adding or changing a region.
- Keep static files intended for direct public access in `public/`; use `src/assets/` for assets imported by Vue components.
- Check desktop and mobile layouts when changing shared navigation, page heroes or the footer.

## Deployment

Build the project:

```bash
npm run build
```

Deploy the generated `dist/` directory to a static hosting provider that supports single-page applications.

For deployments under a subpath, configure Vite's `base` option in `vite.config.js` to match the deployment path. Configure the hosting provider to serve `index.html` as the fallback for client-side routes.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Make and test your changes.
4. Commit your work: `git commit -m "Add: describe your change"`.
5. Push the branch and open a pull request.

Please keep components reusable, preserve existing route conventions and avoid committing secrets or generated local files.

## Maintainer

**Samar Ahmad**

- GitHub: [@Code-Samar](https://github.com/Code-Samar)
- Repository: [Sundarbans-House_Vue](https://github.com/Code-Samar/Sundarbans-House_Vue)
- Live community website: [sundarbans.iitmbs.org](https://sundarbans.iitmbs.org)

---

*Built to bring the Sundarbans House community, events, resources and meetups together in one digital space.*


