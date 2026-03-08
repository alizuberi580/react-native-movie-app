# 🎬 MovieApp

> React Native · Expo SDK 52 · TypeScript · TMDB API · Appwrite · NativeWind

A polished movie discovery app with real-time search, trending analytics, and detailed movie pages — powered by TMDB and Appwrite.

---

## ✨ Features

- **Browse** popular movies in a responsive 3-column grid
- **Search** with debounced input — results update as you type
- **Trending** section driven by real search analytics (Appwrite backend)
- **Movie Details** — poster, rating, runtime, budget, revenue, genres, production companies
- **Tab Navigation** — Home, Search, Save, Profile with custom animated tab bar
- **Styled with NativeWind** (TailwindCSS for React Native)

---

## ⚙️ Stack

- **React Native 0.76** / **Expo SDK 52** / **Expo Router** (file-based routing)
- **TypeScript**
- **NativeWind 4** + TailwindCSS 3
- **TMDB API** — movie data & posters
- **Appwrite** (react-native-appwrite) — trending search tracking
- **Reanimated** · **Gesture Handler** · **MaskedView**

---

## 🗂️ Project Structure

```
app/
  (tabs)/
    index.tsx          → Home screen (trending + latest movies)
    search.tsx         → Debounced search with live results
    save.tsx           → Saved movies
    profile.tsx        → User profile
    _layout.tsx        → Custom tab bar with highlight animation
  movie/[id].tsx       → Dynamic movie detail page

components/
  MovieCard.tsx        → Poster card with rating & year
  TrendingCard.tsx     → Ranked trending card with masked index
  SearchBar.tsx        → Reusable search input

services/
  api.ts               → TMDB fetch (discover, search, details)
  appwrite.ts          → Trending count tracking via Appwrite DB
  usefetch.ts          → Generic async data hook with loading/error/refetch
```

---

## 🚀 Quick Start

**1.** Install dependencies

```bash
npm install
```

**2.** Create `.env` in project root

```env
EXPO_PUBLIC_MOVIE_API_KEY=<your-tmdb-bearer-token>
EXPO_PUBLIC_APPWRITE_PROJECT_ID=<your-appwrite-project-id>
EXPO_PUBLIC_APPWRITE_DATABASE_ID=<your-appwrite-database-id>
EXPO_PUBLIC_APPWRITE_COLLECTION_ID=<your-appwrite-collection-id>
```

**3.** Run

```bash
npx expo start
```

Then press `a` for Android, `i` for iOS, or `w` for web.

---

## 🔑 API Setup

### TMDB

1. Create an account at [themoviedb.org](https://www.themoviedb.org/)
2. Go to Settings → API → generate a **Bearer token** (v4 auth)
3. Set it as `EXPO_PUBLIC_MOVIE_API_KEY`

### Appwrite

1. Create a project at [cloud.appwrite.io](https://cloud.appwrite.io)
2. Create a database with a collection containing these attributes:
   - `searchTerm` (string)
   - `movie_id` (integer)
   - `title` (string)
   - `count` (integer)
   - `poster_url` (string)
3. Copy the project, database, and collection IDs into `.env`

---

## 📦 Key Dependencies

```
expo                     ~52.0
expo-router              ~4.0       → file-based routing
nativewind               ^4.1       → TailwindCSS for RN
react-native-appwrite    ^0.7       → Appwrite SDK
react-native-reanimated  ~3.16      → animations
@react-native-masked-view            → trending card number effect
react-native-heroicons               → icon set
expo-linear-gradient                  → gradient effects
```

---

## 🧪 Tests

```bash
npm test
```

Uses **Jest** + **jest-expo** + **react-test-renderer**.
