# ClearMind - Architecture Document

## Tech Stack

| Layer | Technology | Version |
|---|---|---|
| Frontend | React + TypeScript | React 18.x |
| Styling | Vanilla CSS | - |
| State Management | React Context + Hooks | - |
| Backend | Supabase (BaaS) | - |
| Database | PostgreSQL (via Supabase) | 15.x |
| Authentication | Supabase Auth | - |
| Hosting | Vercel | - |

## Project Structure

```
src/
├── components/       # Shared UI components
│   ├── ui/           # Button, Card, Input, etc.
│   └── layout/       # Header, Footer, Navigation
├── features/         # Feature modules
│   ├── mood/         # Mood tracking feature
│   │   ├── components/
│   │   ├── hooks/
│   │   └── types.ts
│   ├── garden/       # Vườn Tâm Trí feature
│   ├── breathing/    # Breathing exercises
│   └── journal/      # Daily journal
├── hooks/            # Shared hooks
├── lib/              # Utilities, Supabase client
├── styles/           # Global CSS
└── types/            # Shared TypeScript types
```

## Database Schema

### mood_logs
| Column | Type | Description |
|---|---|---|
| id | uuid | Primary key |
| user_id | uuid | FK to auth.users |
| mood_level | int (1-5) | Mood score |
| note | text | Optional note |
| created_at | timestamptz | Entry date |

### garden_items
| Column | Type | Description |
|---|---|---|
| id | uuid | Primary key |
| user_id | uuid | FK to auth.users |
| plant_type | varchar | Type of plant |
| growth_stage | int (1-5) | Growth level |
| habit_type | varchar | Linked habit |
| last_watered | timestamptz | Last interaction |

### journal_entries
| Column | Type | Description |
|---|---|---|
| id | uuid | Primary key |
| user_id | uuid | FK to auth.users |
| content | text | Journal text |
| prompt | text | Daily prompt used |
| sentiment | varchar | positive/neutral/negative |
| created_at | timestamptz | Entry date |

## API Patterns

- Sử dụng Supabase client SDK (không REST trực tiếp)
- Row Level Security (RLS) cho tất cả tables
- Realtime subscriptions cho garden updates

## Coding Conventions

- Component files: PascalCase (e.g., `MoodSelector.tsx`)
- Hook files: camelCase with `use` prefix (e.g., `useMood.ts`)
- CSS files: kebab-case (e.g., `mood-selector.css`)
- Feature folders chứa components, hooks, types riêng
