# Personal Shopper Manager

> Multi-tenant SaaS platform for personal shopping businesses — featuring advanced order management with a high-density data table built for power users.

[![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript)](https://typescriptlang.org)
[![TanStack Table](https://img.shields.io/badge/TanStack_Table-v8-FF4154)](https://tanstack.com/table)
[![Radix UI](https://img.shields.io/badge/Radix_UI-Components-161618)](https://radix-ui.com)
[![Status](https://img.shields.io/badge/Status-Production-brightgreen)]()

---

## Overview

Personal Shopper Manager helps personal shopping businesses track orders, clients, commissions, and logistics across multiple tenants. The core challenge was building a data-dense orders interface that power users could navigate and customize without losing context — solved with a multi-view, column-pinning order module.

Primary tenant: **[amoremioworld.com](https://amoremioworld.com)**

---

## Key Features

### 📋 Orders / Pedidos Module — Multi-View

The order management module offers three distinct views for different working contexts:

| View | Purpose |
|---|---|
| **Tabla** | Standard paginated table for browsing and filtering |
| **Tablero** | Kanban-style board grouped by status |
| **Hoja** | Wide spreadsheet view for bulk review and editing |

### 🗂️ Hoja View — Power User Data Table
Built on **TanStack React Table v8** for maximum performance with large datasets:

- **Horizontal scroll navigation buttons** — jump left/right without trackpad gestures
- **User-controlled column pinning** — drag columns to pin left or right
  - Default: `left: ['cliente']`, `right: ['caja', 'estado']`
  - Persisted via `localStorage` key `pedidos-hoja-column-pinning`
- Sticky pinned columns remain visible while scrolling through wide datasets
- Column visibility toggle — hide/show columns per session

### 🏢 Multi-Tenancy
- Each personal shopping business operates as an isolated tenant
- Tenant routing via custom domain (e.g., `amoremioworld.com`)
- Scoped data access per `tenantId`
- Per-tenant branding and configuration

### 👥 Client Management
- Full client profiles with purchase history
- Order assignment per shopper
- Commission tracking per sale

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 14 (App Router) |
| Language | TypeScript |
| Data Tables | TanStack React Table v8 |
| UI Components | Radix UI |
| Styling | Tailwind CSS |
| Animations | Framer Motion |
| DNS/CDN | Cloudflare |

---

## Architecture Notes

The multi-view orders module is designed so each view (`Tabla`, `Tablero`, `Hoja`) operates independently — state changes in one view do not affect siblings. Column pinning state in the `Hoja` view is persisted to `localStorage` so users return to their preferred layout across sessions.

---

## Status

✅ **Live in production** — primary tenant operational at amoremioworld.com.

---

*Built with Next.js 14, TanStack Table v8, and Claude Code as the primary AI development tool.*
