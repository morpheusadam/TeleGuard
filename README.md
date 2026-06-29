<div align="center">

# 🤖 Laravel Telegram Group Management Bot

### A powerful **Laravel** application for automated **Telegram group management** (TeleGroupBot) — message filtering, keyword moderation, member controls, scheduled messages, and activity insights, with built-in subscriptions and multi-gateway payments.

<p>
  <img src="https://img.shields.io/github/license/morpheusadam/laravel-management-telegram-bot?style=for-the-badge&color=4c1" alt="License" />
  <img src="https://img.shields.io/github/stars/morpheusadam/laravel-management-telegram-bot?style=for-the-badge&color=ffca28" alt="Stars" />
  <img src="https://img.shields.io/github/forks/morpheusadam/laravel-management-telegram-bot?style=for-the-badge&color=42a5f5" alt="Forks" />
  <img src="https://img.shields.io/github/last-commit/morpheusadam/laravel-management-telegram-bot?style=for-the-badge&color=8e44ad" alt="Last commit" />
  <img src="https://img.shields.io/github/repo-size/morpheusadam/laravel-management-telegram-bot?style=for-the-badge&color=e67e22" alt="Repo size" />
</p>

<p>
  <img src="https://img.shields.io/badge/Laravel-8.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white" alt="Laravel" />
  <img src="https://img.shields.io/badge/PHP-7.3%20%7C%208.x-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP" />
  <img src="https://img.shields.io/badge/Telegram-Bot%20API-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram" />
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Redis-Queue-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
  <img src="https://img.shields.io/badge/Pusher-Realtime-300D4F?style=for-the-badge&logo=pusher&logoColor=white" alt="Pusher" />
  <img src="https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
</p>

</div>

---

## 📖 Overview

**Laravel Telegram Group Management Bot** (TeleGroupBot) is a comprehensive, Laravel-based solution for **automating and moderating Telegram groups**. It handles the day-to-day work of running a community — filtering spam, censoring keywords, managing service messages, restricting new members, scheduling announcements, and surfacing member-activity insights — so admins can keep their groups clean, safe, and engaged.

Beyond moderation, the project is built as a **SaaS-ready platform**: it includes a web dashboard, multilingual support, subscriptions/plans, QR-code generation, an update system, and integrations with a wide range of **payment gateways** (PayPal, Stripe, Razorpay, Mollie, Flutterwave, Paystack, Mercado Pago, Xendit, and more). Real-time events are powered by **Pusher**, queues by **Redis/Predis**, and storage can be backed by **AWS S3**.

It's ideal for **community managers, agencies, and developers** who want to offer Telegram group automation as a product or run it for their own communities.

> 🔎 **Keywords:** telegram bot, telegram group management, laravel telegram bot, telegroupbot, group moderation, message filtering, keyword censor, scheduled messages, community management, saas, subscription payments.

---

## ✨ Features

- 🛡️ **Group management** — automate routine tasks to run your Telegram group efficiently.
- 🔒 **Privacy & security** — keep your group protected and well-moderated.
- 🧩 **Customizable** — adapt the bot to the unique needs of each community.
- 🚫 **Advanced message filtering** — automatically filter messages to keep discussion clean and relevant.
- 🔤 **Keyword monitoring** — censor specific words to keep the group respectful.
- 🔔 **Service-message management** — control "user joined" / "user left" and other service messages.
- 👋 **New-member restrictions** — set limits and rules for newcomers.
- ⏰ **Scheduled messages** — broadcast announcements and reminders on a schedule.
- 📊 **Member activity insights** — understand engagement and interaction patterns.
- 🔇 **Ban & mute** — effectively handle problematic members.
- 🌍 **Multilingual** — built-in translation management.
- 💳 **Subscriptions & payments** — multiple gateways (PayPal, Stripe, Razorpay, Mollie, and more).
- 🔗 **Webhook-driven** — receive and process Telegram updates via webhook.

---

## 🛠️ Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=laravel,php,mysql,redis,tailwind,aws,js" alt="Tech stack" />
</p>

| Layer | Technologies |
| --- | --- |
| Backend | Laravel 8, PHP 7.3 / 8.x, Laravel Sanctum, Tinker |
| Messaging | Telegram Bot API (webhook), Pusher (realtime) |
| Queue & Cache | Redis / Predis |
| Storage | AWS SDK, Flysystem S3 |
| Frontend | Blade, Tailwind CSS, Alpine.js, Laravel Mix, SweetAlert2 |
| Payments | PayPal, Stripe, Razorpay, Mollie, Flutterwave, Paystack, Mercado Pago, Xendit, Instamojo, Myfatoorah, Senangpay, Toyyibpay, Paymaya, Yoomoney |
| Utilities | Simple QrCode, LaravelCollective HTML, Joe Dixon Translation |

---

## 🚀 Getting Started

### Prerequisites

- **PHP ≥ 7.3** (8.x recommended) with Composer
- **MySQL ≥ 5.7**
- **Node.js & npm** (for frontend assets)
- A **Telegram bot token** (from [@BotFather](https://t.me/BotFather))

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/morpheusadam/laravel-management-telegram-bot.git
cd laravel-management-telegram-bot

# 2. Install dependencies
composer install
npm install

# 3. Create and configure your environment
cp .env.example .env
php artisan key:generate

# 4. Run migrations (and optionally seed)
php artisan migrate
php artisan db:seed   # optional

# 5. Build assets
npm run dev
```

Start the server and open `http://localhost:8000`:

```bash
php artisan serve
```

> ⚙️ Configure your **Telegram bot token**, **database**, **Pusher**, and **payment gateway** credentials in `.env`, then point your bot's webhook to the app's webhook endpoint.

---

## 🗂️ Project Structure

```text
laravel-management-telegram-bot/
├── app/
│   ├── Http/Controllers/   # Bot, Webhook, Dashboard, Subscription...
│   ├── Providers/Payment/  # PayPal, Stripe, Razorpay, Mollie, ...
│   ├── Models/             # Telegram_bot, Usage_log, User
│   ├── Events/             # ChatEventPusherTelegram / Whatsapp
│   └── Jobs/               # SendEmailJob
├── .github/workflows/      # CI (php.yml)
├── resources/              # Blade views & Tailwind assets
└── routes/                 # web, api & webhook routes
```

---

## 🤝 Contributing

Contributions are welcome! Fork the repository and submit a pull request, or open an [issue](https://github.com/morpheusadam/laravel-management-telegram-bot/issues) with ideas and bug reports.

## 📜 License

Released under the **MIT License** — see the `LICENSE` file (or add one) for details.

---

<div align="center">

### 👤 Author — Morpheus Adam

Web developer & cheerful hacker · PHP · Laravel · Go

<p>
  <a href="https://github.com/morpheusadam"><img src="https://img.shields.io/badge/GitHub-morpheusadam-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://sam.zeonic.me"><img src="https://img.shields.io/badge/Website-sam.zeonic.me-4c1?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website" /></a>
  <a href="mailto:morpheusadam95@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</p>

⭐ **If this bot helps you manage your Telegram community, please give it a star!** ⭐

</div>
