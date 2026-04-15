<template>
  <div>
    <PageHero
      bg-image="https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=1920&q=80&auto=format&fit=crop"
      breadcrumb-title="Events"
      title="Events &"
      accent-title="Activities"
      subtitle="Workshops, competitions, meetups and so much more awaits you"
    />

    <!-- Featured Event -->
    <section class="section rs" style="background: var(--bg2)">
      <div class="container">
        <div class="sec-hdr">
          <div class="section-tag">Next Big Event</div>
          <h2 class="section-title-xl">
            Upcoming <span class="tg">Highlight</span>
          </h2>
        </div>
        <div
          class="card-base rs"
          style="
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
            border: 1px solid rgba(79, 142, 247, 0.3);
          ">
          <div>
            <img
              src="https://images.unsplash.com/photo-1475721027785-f74eccf877e2?w=700&q=80&auto=format&fit=crop"
              alt="AI Conference"
              style="
                width: 100%;
                border-radius: 12px;
                aspect-ratio: 16/9;
                object-fit: cover;
              " />
          </div>
          <div>
            <div class="section-tag">Featured</div>
            <h3
              style="
                font-family: Cinzel, serif;
                font-size: 1.8rem;
                font-weight: 800;
                margin: 0.75rem 0;
              ">
              Guest Lecture: AI &amp; Machine Learning
            </h3>
            <p class="desc">
              Exclusive talk by IIT Madras faculty — deep dive into the future
              of AI, research opportunities and career paths in machine
              learning.
            </p>
            <div style="margin: 1.5rem 0">
              <div id="mainEventCountdown" class="countdown-widget"></div>
            </div>
            <div
              style="
                display: flex;
                gap: 0.75rem;
                flex-wrap: wrap;
                margin-bottom: 1.25rem;
              ">
              <span style="font-size: 0.8rem; color: var(--text2)"
                >📅 This Friday, 6:00 PM – 8:00 PM</span
              >
              <span style="font-size: 0.8rem; color: var(--text2)"
                >📍 Online (Zoom)</span
              >
              <span style="font-size: 0.8rem; color: var(--text2)"
                >🎟️ Free for all members</span
              >
            </div>
            <a href="#" class="btn-hero-primary" style="display: inline-flex"
              >Register Now →</a
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Upcoming Events -->
    <section class="section rs">
      <div class="container">
        <div
          style="
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 2rem;
            flex-wrap: wrap;
            gap: 1rem;
          ">
          <div>
            <div class="section-tag">What's On</div>
            <h2 class="section-title-xl" style="margin: 0">
              Upcoming <span class="tg">Events</span>
            </h2>
          </div>
          <div class="filter-tabs">
            <div
              class="ftab"
              v-for="tab in tabs"
              :key="tab"
              :class="{ active: activeTab === tab }"
              @click="activeTab = tab">
              {{ tab }}
            </div>
          </div>
        </div>
        <div class="grid-3">
          <div
            class="card-base rc"
            v-for="(ev, i) in filteredEvents"
            :key="ev.title"
            :style="`--card-delay:${(i + 1) * 0.1}s`">
            <div
              style="
                height: 160px;
                border-radius: 10px;
                overflow: hidden;
                margin-bottom: 1rem;
              ">
              <img
                :src="ev.img"
                :alt="ev.title"
                style="width: 100%; height: 100%; object-fit: cover" />
            </div>
            <div class="section-tag" :style="ev.tagStyle || ''">
              {{ ev.category }}
            </div>
            <h3
              style="
                font-family: Cinzel, serif;
                font-weight: 700;
                margin: 0.5rem 0 0.4rem;
              ">
              {{ ev.title }}
            </h3>
            <p class="desc" style="margin-bottom: 0.75rem">{{ ev.desc }}</p>
            <div
              style="
                display: flex;
                gap: 1rem;
                margin-bottom: 1rem;
                font-size: 0.8rem;
                color: var(--text2);
              ">
              <span>📅 {{ ev.date }}</span
              ><span>🕐 {{ ev.time }}</span
              ><span>📍 {{ ev.location }}</span>
            </div>
            <a
              href="#"
              class="submit-btn"
              style="font-size: 0.85rem; padding: 0.55rem 1.25rem"
              >Register Now</a
            >
          </div>
        </div>
      </div>
    </section>

  <!-- Past Events -->
<section class="section rs" style="background: var(--bg2)">
  <div class="container">
    <div class="sec-hdr">
      <div class="section-tag">Memories</div>
      <h2 class="section-title-xl">Past <span class="tg">Events</span></h2>
    </div>
    <div class="grid-3">
      <div
        class="card-base rc"
        v-for="(p, i) in pastEvents"
        :key="p.title"
        :style="`--card-delay:${(i % 6) * 0.08}s`"
        style="display:flex; flex-direction:column; padding:0; overflow:hidden;">

        <!-- Image banner with icon overlay -->
        <div style="position:relative; height:140px; background: linear-gradient(135deg, rgba(212,160,23,0.12), rgba(8,7,5,0.9)); flex-shrink:0; display:flex; align-items:center; justify-content:center;">
          <span style="font-size:2.8rem; filter: drop-shadow(0 2px 8px rgba(0,0,0,0.5))">{{ p.icon }}</span>
          <!-- date badge -->
          <span style="position:absolute; top:10px; right:12px; font-size:0.7rem; background:rgba(212,160,23,0.15); color:var(--accent2); border:1px solid rgba(212,160,23,0.3); border-radius:20px; padding:2px 10px; font-weight:600; letter-spacing:0.03em;">
            {{ p.date }}
          </span>
        </div>

        <!-- Content -->
        <div style="padding: 1rem 1.25rem 1.25rem; display:flex; flex-direction:column; flex:1;">
          <div class="section-tag" style="margin-bottom:0.5rem; background:rgba(212,160,23,0.06); color:var(--text2); border-color:rgba(212,160,23,0.2);">
            Past Event
          </div>
          <h4 style="font-family:Cinzel,serif; font-weight:700; font-size:0.95rem; margin-bottom:0.5rem; line-height:1.4;">
            {{ p.title }}
          </h4>
          <p class="desc" style="font-size:0.82rem; flex:1; margin-bottom:0;">
            {{ p.desc }}
          </p>
        </div>

      </div>
    </div>
  </div>
</section>

    <!-- Host CTA -->
    <section
      class="cta-section rs"
      style="
        padding: 5rem 0;
        background: linear-gradient(
          135deg,
          rgba(212, 160, 23, 0.06),
          rgba(8, 7, 5, 0.95)
        );
      ">
      <div class="container">
        <div class="cta-wrap">
          <div class="section-tag light">Got an idea?</div>
          <h2 class="cta-heading">
            Host Your Own <span class="cta-acc">Event</span>
          </h2>
          <p class="cta-sub">
            Have an idea for a workshop, talk, or meetup? We support student-led
            initiatives. Submit your proposal and we'll make it happen.
          </p>
          <div class="cta-acts">
            <router-link to="/contact" class="cta-btn-p"
              >Submit Proposal →</router-link
            >
            <router-link to="/contact" class="cta-btn-o"
              >Talk to Team</router-link
            >
          </div>
        </div>
      </div>
    </section>


  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";
import PageHero from "../components/PageHero.vue";

import { useScrollReveal } from "../composables/useAnimations.js";
useScrollReveal();

const tabs = ["All", "Workshops", "Meetups", "Competitions", "Talks"];
const activeTab = ref("All");

const allEvents = [
  {
    title: "Python for Beginners",
    category: "Workshop",
    date: "Mar 15",
    time: "6–8 PM",
    location: "Virtual",
    img: "https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?w=500&q=80&auto=format&fit=crop",
    desc: "Learn Python from scratch — hands-on exercises and real projects",
    type: "Workshops",
  },
  {
    title: "Inter-House Quiz",
    category: "Competition",
    date: "Mar 20",
    time: "5–7 PM",
    location: "Virtual",
    img: "https://images.unsplash.com/photo-1434626881859-194d67b2b86f?w=500&q=80&auto=format&fit=crop",
    desc: "Battle of knowledge — test your skills across multiple domains",
    type: "Competitions",
  },
  {
    title: "Delhi Meetup 2026",
    category: "Offline Meetup",
    tagStyle:
      "background:rgba(245,158,11,0.1);color:#F59E0B;border-color:rgba(245,158,11,0.3)",
    date: "Apr 10",
    time: "4 PM",
    location: "Delhi",
    img: "https://images.unsplash.com/photo-1587474260584-136574528ed5?w=500&q=80&auto=format&fit=crop",
    desc: "Network with Sundarbans members in Delhi — food, fun and friendships",
    type: "Meetups",
  },
  {
    title: "Chennai Meetup 2026",
    category: "Offline Meetup",
    tagStyle:
      "background:rgba(245,158,11,0.1);color:#F59E0B;border-color:rgba(245,158,11,0.3)",
    date: "Mar 25",
    time: "3 PM",
    location: "Chennai",
    img: "https://images.unsplash.com/photo-1529253355930-ddbe423a2ac7?w=500&q=80&auto=format&fit=crop",
    desc: "Connect with fellow students in Chennai — sessions, games and more",
    type: "Meetups",
  },
  {
    title: "SundarHack 2026",
    category: "Hackathon",
    date: "Apr 25–27",
    time: "All weekend",
    location: "Virtual",
    img: "https://images.unsplash.com/photo-1531482615713-2afd69097998?w=500&q=80&auto=format&fit=crop",
    desc: "48-hour coding marathon — build, break, and innovate with your team",
    type: "Competitions",
  },
  {
    title: "Career in Research",
    category: "Guest Talk",
    date: "May 5",
    time: "7–9 PM",
    location: "Virtual",
    img: "https://images.unsplash.com/photo-1475721027785-f74eccf877e2?w=500&q=80&auto=format&fit=crop",
    desc: "PhD scholars discuss research life, opportunities and how to get started",
    type: "Talks",
  },
];

const filteredEvents = computed(() =>
  activeTab.value === "All"
    ? allEvents
    : allEvents.filter((e) => e.type === activeTab.value),
);

const pastEvents = [
  {
    icon: "💪",
    title: "Shakti Series — Episode 1",
    desc: "Inaugural session of the empowerment series celebrating strength, resilience and community spirit",
    date: "October 2025",
  },
  {
    icon: "🪔",
    title: "Navrang 2.0 — Celebrate Navratri with Boundless!",
    desc: "Nine nights of vibrant cultural celebration featuring dance, music and festive traditions",
    date: "September 2025",
  },
  {
    icon: "🇮🇳",
    title: "Pre-Independence Day Session — Capt. Albert Louis",
    desc: "Inspiring talk by Capt. Albert Louis on patriotism, sacrifice and the journey of our nation",
    date: "August 2025",
  },
  {
    icon: "🏸",
    title: "Paradox Badminton League 2.0",
    desc: "Inter-house badminton tournament with intense rallies and fierce competition across divisions",
    date: "May 2025",
  },
  {
    icon: "🏏",
    title: "IPL Auction Showdown — Bid. Strategise. Conquer.",
    desc: "Strategic mock IPL auction where participants built dream teams with limited budgets",
    date: "May 2025",
  },
  {
    icon: "🏃",
    title: "Kampus Run — Run Clean. Run Green.",
    desc: "Community marathon promoting fitness and environmental awareness among students",
    date: "May 2025",
  },
  {
    icon: "⚽",
    title: "Paradox Champions League — Football Faceoff",
    desc: "High-energy inter-house football championship with knockout rounds and thrilling finals",
    date: "May 2025",
  },
  {
    icon: "🛡️",
    title: "Ghost in the Firewall — Cybersecurity Challenge",
    desc: "Capture-the-flag style cybersecurity contest testing ethical hacking and digital forensics skills",
    date: "May 2025",
  },
  {
    icon: "💻",
    title: "Hack Eclipse — 24-hour Hackathon",
    desc: "Round-the-clock coding marathon where teams built innovative solutions to real-world problems",
    date: "May 2025",
  },
  {
    icon: "🎖️",
    title: "Into the Shadows — Special Forces Talk",
    desc: "Exclusive session on India's Special Forces — their training, missions and the warrior mindset",
    date: "February 2025",
  },
  {
    icon: "📸",
    title: "FrameQuest — Photography Contest",
    desc: "Creative photography challenge showcasing diverse perspectives through the lens",
    date: "February 2025",
  },
  {
    icon: "🐍",
    title: "Python Odyssey — Join the Coding Journey",
    desc: "Beginner-friendly Python workshop covering fundamentals, hands-on exercises and mini-projects",
    date: "February 2025",
  },
  {
    icon: "📖",
    title: "How old is the Mahabharata? — Talk by Nilesh Oak",
    desc: "Fascinating talk by author Nilesh Oak exploring astronomical dating of the Mahabharata era",
    date: "January 2025",
  },
  {
    icon: "🇮🇳",
    title: "Frames of Freedom — Republic Day Photography",
    desc: "Patriotic photography contest capturing the spirit of Republic Day through powerful imagery",
    date: "January 2025",
  },
  {
    icon: "👩‍💼",
    title: "Navodaya — A New Dawn of Women in Leadership",
    desc: "Panel discussion celebrating women leaders and their journeys in breaking barriers",
    date: "December 2024",
  },
  {
    icon: "🎤",
    title: "Dinkar ki Pratiksha — Inter-House Open Mic",
    desc: "Open mic night featuring poetry, storytelling and spoken word performances across houses",
    date: "September 2024",
  },
  {
    icon: "🌟",
    title: "Sundarbans BS Talent Show",
    desc: "Grand showcase of hidden talents — singing, dancing, comedy and creative performances",
    date: "July 2024",
  },
  {
    icon: "🧘",
    title: "How to Improve Concentration — Swami Mukundanand Ji",
    desc: "Spiritual wisdom session on focus, mindfulness and techniques to sharpen concentration",
    date: "March 2023",
  },
];

// Countdown
let cdTimer = null;
function updateCd() {
  const el = document.getElementById("mainEventCountdown");
  if (!el) return;
  const now = new Date();
  const fri = new Date();
  fri.setDate(now.getDate() + ((5 - now.getDay() + 7) % 7) || 7);
  fri.setHours(18, 0, 0, 0);
  const diff = fri - now;
  if (diff <= 0) {
    el.innerHTML = '<span class="cd-over">Event Started!</span>';
    return;
  }
  const d = Math.floor(diff / 86400000),
    h = Math.floor((diff % 86400000) / 3600000);
  const m = Math.floor((diff % 3600000) / 60000),
    s = Math.floor((diff % 60000) / 1000);
  el.innerHTML = `<div class="cd-unit"><span class="cd-num">${String(d).padStart(2, "0")}</span><span class="cd-label">days</span></div><div class="cd-sep">:</div><div class="cd-unit"><span class="cd-num">${String(h).padStart(2, "0")}</span><span class="cd-label">hrs</span></div><div class="cd-sep">:</div><div class="cd-unit"><span class="cd-num">${String(m).padStart(2, "0")}</span><span class="cd-label">min</span></div><div class="cd-sep">:</div><div class="cd-unit"><span class="cd-num">${String(s).padStart(2, "0")}</span><span class="cd-label">sec</span></div>`;
}
onMounted(() => {
  updateCd();
  cdTimer = setInterval(updateCd, 1000);
});
onUnmounted(() => clearInterval(cdTimer));
</script>
