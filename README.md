# MentorsArena — Graduation Project

**A Laravel-based learning platform with course, instructor and learner workflows.**

## Overview

This graduation-project repository contains a learning-management application. Its configured application name is **MentorsArena**. The codebase includes course and webinar content, learner and instructor areas, quizzes, certificates, meetings, commerce and administration.

## Functional areas

- Course and webinar discovery, content and enrolment-related models.
- Learner and instructor workspaces.
- Quizzes, results, assignments and certificates.
- Meeting and live-session integrations.
- Orders, subscriptions and payment-provider integrations.
- Multilingual content, support and administration.

These are areas represented in the checked-in routes and models. External integrations require their own configuration and credentials.

## Technology

| Layer | Declared stack |
| --- | --- |
| Backend | Laravel `^7.0` · PHP `^7.2.5` |
| Assets | Laravel Mix 5 · webpack · Sass · Bootstrap |
| Data | Eloquent ORM · MySQL configuration |
| Integrations | Payment gateways, meeting providers and messaging SDKs |

Use [composer.json](composer.json), `composer.lock` and [package.json](package.json) to reproduce the original dependency set. This is a legacy application snapshot; the PHP declaration is a historical dependency constraint rather than a recommendation for a new deployment.

## Local setup

```bash
git clone https://github.com/Moelnabawy8/Graduation-Project.git
cd Graduation-Project
composer install
cp .env.example .env
php artisan key:generate
npm install
npm run dev
```

Configure a dedicated local MySQL database and the application's base URL in your local environment. The full application needs its original schema and required settings data; migration files alone should not be assumed to recreate a populated installation. Obtain a sanitised development schema through the project maintainer.

Once configuration and schema are ready:

```bash
php artisan storage:link
php artisan serve
```

The development server is available at `http://127.0.0.1:8000`. Payment, video, storage and messaging integrations should be configured separately for local testing.

## Code guide

| Path | Responsibility |
| --- | --- |
| [`routes/web.php`](routes/web.php) | Public website and course routes |
| [`routes/panel.php`](routes/panel.php) | User workspace routes |
| [`routes/admin.php`](routes/admin.php) | Administration |
| [`routes/api/`](routes/api/) | API route groups |
| [`app/Models/`](app/Models/) | Learning, commerce and platform entities |
| [`resources/views/`](resources/views/) | Application templates |

## Verification and attribution

PHPUnit scaffolding is included under [`tests/`](tests/), configured by [phpunit.xml](phpunit.xml). Run it with `./vendor/bin/phpunit` in a compatible local environment with an isolated testing database.

For asset compilation use `npm run dev` during development or `npm run production` for the production asset build.

The repository includes framework code, packages and bundled assets from third parties. Their licences and notices continue to apply. A portfolio case study should identify the specific features contributed to the graduation project.
