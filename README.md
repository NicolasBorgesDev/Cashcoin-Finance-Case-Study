# 💰 Cashcoin - Smart Personal Finance & Wealth Management (Case Study)

> **Note:** The source code for this project is private due to proprietary business logic. This repository serves as a technical case study highlighting the software architecture, responsive UI design, and advanced data-handling methodologies used to build the platform.

## 📖 Overview
Cashcoin is a robust, premium personal finance web application. It goes beyond basic expense tracking by introducing advanced features like an intelligent credit card engine, predictive budgeting, mid-to-long-term goal tracking, and multi-currency support (USD/EUR/BRL). Designed with a modern, neobank-inspired interface, the application prioritizes performance, fluid usability, and strict data security.

---

<p align="center">
  <img width="100%" alt="Captura de tela 2026-10-23 165204" src="https://github.com/user-attachments/assets/ca9b51c7-5fed-4a47-a9a2-e23908e19535" />
</p>
<p align="center">
  <img width="49%" alt="Captura de tela 2026-10-23 165654" src="https://github.com/user-attachments/assets/75d6f0d8-01eb-4655-9036-c29410b5231b" />
  <img width="49%" alt="Captura de tela 2026-10-23 165725" src="https://github.com/user-attachments/assets/dcf087a6-a0e0-4d82-af43-e5628457af71" />
</p>

---

## 🚀 Key Features & Technical Highlights

- **Intelligent Credit Card Engine:** Treats credit cards as temporal entities with complex billing cycles. It dynamically calculates which invoice a transaction belongs to based on the "best purchase day" and groups transactions seamlessly on the ledger.
- **Predictive Budgeting & Goal Tracking:** Real-time budget monitoring with dynamic UI alerts (via Tailwind CSS) when spending limits are approached. It projects completion deadlines for financial goals based on active contribution rhythms.
- **Multi-Currency Normalization:** Implements custom exchange rate logic to instantly convert and normalize foreign transactions (e.g., USD/EUR) into base currency (BRL) for accurate dashboard reporting.
- **Advanced Receipt Management:** Secure inline viewing of PDFs and images directly within the app (using a custom AttachmentModal). It leverages Supabase Storage with strict RLS policies, ensuring raw bucket URLs are never exposed.

## 🛠️ Tech Stack & Architecture
Built entirely on a modern, highly scalable JavaScript ecosystem.

### Frontend
- **Core:** React 18, TypeScript, Vite
- **State Management:** Zustand (global UI/privacy states) & Custom Hooks for complex async queries.
- **Routing:** React Router DOM (Fluid SPA experience)
- **UI/UX:** Tailwind CSS (Glassmorphism, dynamic dark mode), Lucide React, Google Fonts
- **Data Visualization:** Recharts (Dynamic and interactive dashboards)

### Backend & Database (Supabase BaaS)
- **Database:** PostgreSQL (Relational)
- **Authentication:** Supabase Auth
- **Security:** Stringent Row Level Security (RLS) guaranteeing that authenticated users can only query, insert, or view records and storage buckets that strictly belong to their `user_id`.

<p align="center">
  <img width="100%" alt="Captura de tela 2026-10-23 165231" src="https://github.com/user-attachments/assets/fca0e0f9-4706-41ed-a95b-d041bca30a14" />
</p>

## 🧠 Architectural Solutions
- **Reactive UI & State Invalidation:** Complex relationships between Accounts, Transactions, and Credit Cards are managed through state subscription techniques. Paying a grouped invoice instantly updates credit limits and account balances without requiring a page reload.
- **Dynamic Institution Mapping:** Implemented a regex-based engine that scans transaction descriptions to dynamically assign the correct bank logo and brand color (from a static dictionary), eliminating manual data entry.

<p align="center">
  <img width="49%" alt="Captura de tela 2026-10-23 165252" src="https://github.com/user-attachments/assets/31af4ad7-6ed2-4215-9b69-dd3eae9af5fc" />
  <img width="49%" alt="Captura de tela 2026-10-23 165337" src="https://github.com/user-attachments/assets/d7f0a2a5-b81d-41ca-a695-90c375bb7ae7" />
</p>
<p align="center">
  <img width="49%" alt="Captura de tela 2026-10-23 165310" src="https://github.com/user-attachments/assets/216012ad-1e8b-48ec-8e1f-745ad3d15bda" />
  <img width="49%" alt="Captura de tela 2026-10-23 165355" src="https://github.com/user-attachments/assets/24e55c90-ccbd-4c7b-b776-b12144d3858d" />
</p>

