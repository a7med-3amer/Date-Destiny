# Date & Destiny ✨ — Discover Your Birthday Story

[![Next.js](https://img.shields.io/badge/Next.js-16.3.8-black?style=flat&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.2.8-blue?style=flat&logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?style=flat&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38bdf8?style=flat&logo=tailwind-css)](https://tailwindcss.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-green?style=flat&logo=mongodb)](https://www.mongodb.com/)

**Date & Destiny** is a production-quality, full-stack web application that transforms an ordinary date of birth into an extraordinary story of self-discovery, historical wonder, and personalized inspiration.

---

## 🌟 Core Features

### 1. Accurate Age & Biological Rhythms
- **Exact Age Breakdown**: Precise years, months, and days calculated with calendar accuracy (taking leap years and varying month lengths into account).
- **Time Elapsed**: Total days, total weeks, total hours, total minutes, and total seconds lived.
- **Biological Rhythm Approximations**: Estimated lifetime heartbeats (~78 bpm) and breaths taken (~16 bpm).
- **Day of the Week**: Identifies the day you were born, accompanied by traditional cultural nursery lore.

### 2. "People Who Share Your Birthday 🌟"
- Curated and dynamically fetched verified figures from the official **Wikimedia REST API**.
- Includes real photos, birth/death years, professions, and short biographical overviews.
- Features quick search filtering and direct links to deep-dive biography articles.
- Zero invented facts or fictitious figures.

### 3. "Your Date Has a Story 📖"
- **Western Zodiac**: Sign, astrological symbol, element (Fire, Earth, Air, Water), ruling planet, modality, and key personality traits.
- **Chinese Zodiac**: Lunar calendar animal, element, and symbolic attributes.
- **Birthstone**: Gemstone name, official color preview, meaning, and historical lore.
- **Birth Flower**: Traditional flower, symbolism, and botanical meaning.
- **Season of Birth**: Meteorological season and exact position in the 365/366-day calendar year with a visual progress bar.
- **Historical Events**: World-shaping milestones that occurred on that date throughout human history.

### 4. "A Little Message For You 💌"
- Thoughtful, warm, and cute motivational messages tailored specifically to the user's life stage (Youth, Twenties, Thirties, Midlife, Senior, Universal).
- Reusable dynamic message system with a **"Show Another Message 💫"** button that shuffles fresh quotes on demand.
- One-click **"Copy to Clipboard"** functionality.

### 5. "Your Next Birthday 🎉" Live Countdown
- Real-time live ticking countdown (Days, Hours, Minutes, Seconds) until the user's next birthday.
- **Birthday Edge-Case Detection**: If today is their birthday, the interface transforms into a celebratory party banner with confetti!
- Leap-year baby support: Feb 29 birthdays correctly target March 1 in non-leap years.

### 6. Visual Life Timeline
- A chronological milestone journey dynamically computed from the user's birth year:
  - `Birth Year` — The Story Begins 👶
  - `~Age 6` — First Steps into Knowledge 📚
  - `~Age 13` — Teenage Horizons 🎧
  - `~Age 18` — Stepping into Adulthood 🎓
  - `~Age 21` — Coming of Age & Ambition 🌟
  - `~Age 25+` — Quarter Century Milestone 🧭
  - `Current Year` — Today ⭐ (Highlights the current chapter)
  - `Future` — More Chapters to Come 🚀

### 7. Polished SaaS Design & Dark Mode
- Apple-inspired minimalism with soft gradients and glassmorphism.
- Responsive design tailored for mobile, tablet, and widescreen desktop monitors.
- Full dark and light mode toggle with zero flicker and localStorage persistence.
- Interactive celebration confetti powered by `canvas-confetti`.

---

## 🏗️ Architecture & Project Structure

```
/
├── app/
│   ├── api/
│   │   ├── date-info/route.ts      # GET /api/date-info?date=YYYY-MM-DD
│   │   ├── famous-people/route.ts  # GET /api/famous-people?month=MM&day=DD
│   │   ├── facts/route.ts          # GET /api/facts?month=MM&day=DD&year=YYYY
│   │   ├── messages/route.ts       # GET /api/messages?age=X&exclude=ID
│   │   ├── save-date/route.ts      # POST /api/save-date
│   │   └── db-status/route.ts      # GET /api/db-status (Health check)
│   ├── discover/
│   │   └── page.tsx                # Results Dashboard page
│   ├── about/
│   │   └── page.tsx                # About & Methodology page
│   ├── globals.css                 # Design tokens & glassmorphism utilities
│   ├── layout.tsx                  # Root layout with SEO & Navbar/Footer
│   └── page.tsx                    # Landing page with hero & date picker
├── components/
│   ├── Navbar.tsx                  # Responsive navigation with dark mode switch
│   ├── Footer.tsx                  # Footer with links & privacy statement
│   ├── ThemeToggle.tsx             # Dark/Light mode toggle
│   ├── DatePickerForm.tsx          # 3-field date picker with validation
│   ├── StatsCards.tsx              # Animated counter cards & biological rhythms
│   ├── HeroDashboard.tsx           # Birthday headline & celebration trigger
│   ├── LiveCountdown.tsx           # Live real-time birthday countdown
│   ├── FamousPeopleSection.tsx     # Birthday twins with photos and bios
│   ├── DateStorySection.tsx        # Zodiac, birthstone, flowers, and lore
│   ├── PositiveMessageCard.tsx     # Personalized message & refresh system
│   ├── LifeTimeline.tsx            # Visual life milestone timeline
│   ├── CelebrationConfetti.tsx     # Canvas confetti particles
│   └── LoadingSkeleton.tsx         # Shimmer skeletons for loading states
├── lib/
│   ├── dateCalculations.ts         # Exact calendar arithmetic & timeline generator
│   ├── factsData.ts                # Zodiac, birthstones, flowers, poems data
│   ├── messagesData.ts             # Curated age-appropriate inspirational messages
│   ├── famousPeopleData.ts         # Verified seed database of famous figures
│   ├── wikiService.ts              # Wikimedia REST API integration
│   └── mongodb.ts                  # Mongoose connection with resilient fallback
├── models/
│   ├── UserSubmission.ts           # Anonymous submission model
│   ├── FamousPerson.ts             # Famous person cache model
│   ├── PositiveMessage.ts          # Positive message model
│   └── DateFact.ts                 # Date facts model
├── services/
│   └── dateService.ts              # Business logic orchestrator
├── types/
│   └── index.ts                    # TypeScript interfaces & types
├── utils/
│   ├── formatters.ts               # Number and date string formatting
│   └── validation.ts               # Leap year & date validity rules
├── scripts/
│   └── seed.mjs                    # MongoDB database seeder script
├── .env.example                    # Template for environment variables
└── README.md                       # Comprehensive project documentation
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js**: v18.18+ or v20+ (tested on Node v24 LTS)
- **npm** or **pnpm** or **yarn**
- **MongoDB** (optional; the app features an automatic in-memory fallback if no MongoDB server is running)

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd App1
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   Create a `.env.local` file (or copy from `.env.example`):
   ```bash
   cp .env.example .env.local
   ```
   Default settings:
   ```env
   MONGODB_URI=mongodb://localhost:27017/date_and_destiny
   NEXT_PUBLIC_APP_URL=http://localhost:3000
   NODE_ENV=development
   ```

4. **Seed MongoDB (Optional)**:
   If you have a local or cloud MongoDB instance running:
   ```bash
   npm run seed
   ```

5. **Start the development server**:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

6. **Build for production**:
   ```bash
   npm run build
   npm run start
   ```

---

## 📡 REST API Documentation

### 1. `GET /api/date-info?date=YYYY-MM-DD`
Calculates comprehensive date statistics, age breakdown, birthday countdown, verified famous twins, and life timeline.

**Example Request**:
```http
GET /api/date-info?date=2003-05-14
```

**Example Response**:
```json
{
  "success": true,
  "date": "2003-05-14",
  "age": {
    "years": 23,
    "months": 4,
    "days": 19
  },
  "totalDays": 8543,
  "totalWeeks": 1220,
  "totalHours": 205032,
  "totalMinutes": 12301920,
  "totalSeconds": 738115200,
  "approxHeartbeats": 959549760,
  "approxBreaths": 196830720,
  "nextBirthday": "2027-05-14",
  "nextBirthdayFormatted": "Friday, May 14, 2027",
  "daysUntilBirthday": 223,
  "turningAge": 24,
  "dayOfWeek": "Wednesday",
  "isTodayBirthday": false,
  "facts": {
    "dayOfWeek": "Wednesday",
    "dayOfWeekPoem": "Wednesday's child is full of woe (traditionally meaning empathy and depth of heart).",
    "season": "Spring",
    "zodiac": {
      "sign": "Taurus",
      "symbol": "♉",
      "element": "Earth",
      "rulingPlanet": "Venus",
      "traits": ["Reliable", "Patient", "Devoted", "Sensual", "Grounded"]
    },
    "birthstone": {
      "stone": "Emerald",
      "colorName": "Vibrant Forest Green",
      "meaning": "Rebirth, renewal, and deep intuition."
    },
    "historicalEvents": [ ... ]
  },
  "famousPeople": [ ... ],
  "message": {
    "id": "msg-20-1",
    "text": "You don't have to have everything figured out. You're allowed to grow at your own pace. 💙",
    "theme": "encouragement",
    "ageGroup": "twenties"
  },
  "timeline": [ ... ]
}
```

### 2. `GET /api/famous-people?month=MM&day=DD`
Returns verified historical figures born on the specified month and day.

### 3. `GET /api/facts?month=MM&day=DD&year=YYYY`
Returns astronomical, botanical, and historical lore for the date.

### 4. `GET /api/messages?age=X[&exclude=ID]`
Returns a motivational quote for the given age bracket.

### 5. `POST /api/save-date`
Body: `{ "date": "YYYY-MM-DD" }` — Anonymously registers a birthdate entry in MongoDB.

### 6. `GET /api/db-status`
Returns database connection status and collection document counts.

---

## 🛡️ Edge Cases & Validation Rules

- **Leap Year Calculations**: Correctly recognizes leap years (e.g. Feb 29, 2004). Feb 29 on non-leap years (e.g. 2003) is rejected with a friendly error.
- **Different Month Lengths**: Enforces 28, 29, 30, and 31-day months (e.g. April 31 is rejected).
- **Future Date Prevention**: Dates later than the current calendar day are rejected with clear user guidance.
- **Reasonable Range**: Rejects birth years prior to 1900.
- **Birthday Today**: Automatically detects when today is the user's birthday, displaying a party hero banner and launching fireworks.

---

## 🔒 Security & Privacy

- **Input Sanitization**: All queries and date components are strictly parsed and validated.
- **Credential Protection**: MongoDB connection strings and secrets are kept in environment variables and excluded via `.gitignore`.
- **Zero Mandatory Tracking**: No cookies, tracking pixels, or forced account creation.

---

## 📄 License
MIT License. Created with ❤️ for curious minds everywhere.
