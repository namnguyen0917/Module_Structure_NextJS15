# Module Structure NextJS 15 +
├─ src/
│  ├─ app/                         # App Router (route-level)
│  │  ├─ layout.tsx               # Root layout – import globals.css, Redux Provider
│  │  ├─ page.tsx                 # Trang Landing/Index
│  │  ├─ (marketing)/             # Group routes công khai
│  │  │  └─ about/
│  │  │     └─ page.tsx
│  │  └─ (dashboard)/             # Group routes cần auth (middleware protect)
│  │     ├─ layout.tsx            # Layout riêng cho dashboard
│  │     └─ page.tsx
│  ├─ features/                   # TÁCH THEO CHỨC NĂNG (Redux + UI + service)
│  │  ├─ auth/
│  │  │  ├─ components/
│  │  │  │  ├─ LoginForm.tsx
│  │  │  │  └─ RegisterForm.tsx
│  │  │  ├─ slices/               # Redux slice
│  │  │  │  └─ authSlice.ts
│  │  │  ├─ hooks/
│  │  │  │  └─ useAuth.ts
│  │  │  └─ services/             # API calls (fetch/axios/tRPC client)
│  │  │     └─ authApi.ts
│  │  ├─ products/
│  │  │  ├─ components/
│  │  │  │  └─ ProductCard.tsx
│  │  │  ├─ slices/
│  │  │  │  └─ productSlice.ts
│  │  │  └─ services/
│  │  │     └─ productApi.ts
│  │  └─ cart/
│  │     └─ …
│  ├─ shared/
│  │  ├─ components/
│  │  │  ├─ ui/                   # Button, Input… (shadcn hoặc tùy)
│  │  │  └─ layout/               # Header, Footer, Sidebar
│  │  ├─ hooks/                   # useDebounce, useWindowSize…
│  │  ├─ lib/                     # axiosClient.ts, formatters.ts
│  │  └─ types/
│  │     └─ index.ts
│  ├─ store/                      # Redux Toolkit store
│  │  ├─ index.ts                 # configureStore + rootReducer
│  │  └─ middleware.ts            # logger, authGuard…
│  ├─ styles/
│  │  ├─ globals.css              # Tailwind base + custom
│  │  └─ tailwind.config.cjs
│  ├─ middleware.ts               # Next.js edge middleware (auth, i18n…)
│  └─ utils/                      # small pure helpers không phụ thuộc React
├─ public/                        # ảnh, font, favicon
├─ .env.local
├─ tsconfig.json                  # alias path: @features/*, @shared/*
└─ next.config.mjs
