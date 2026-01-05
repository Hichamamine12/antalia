# Copilot Instructions - Tadbir Al Mohassaba

## Project Overview
**Tadbir Al Mohassaba** is a single-page accounting management application (web-based dashboard) for Moroccan businesses. It provides modules for invoice management, accounting, client records, products, and settings—all currently in one HTML file.

## Architecture

### Current Structure
- **Single-file architecture**: All HTML, CSS, and JavaScript in `index (2).html`
- **SPA pattern**: Navigation via data-page attributes without page reloads
- **Language**: French UI with Arabic name
- **No external libraries**: Vanilla JS, Remixicon icons, Google Fonts

### Key Components
1. **Sidebar Navigation** - Dark theme (color `#0d1b2a`), fixed width 260px, icon-based menu
2. **Main Content Area** - Flex layout with scrollable pages
3. **Page Switching** - Event-driven visibility toggle (add/remove `.active` class)

## Development Patterns

### Navigation System
Pages are managed via CSS class toggling:
- Each nav item has `data-page` attribute
- Corresponding section has matching `id`
- Click listener removes `.active` from all, adds to clicked nav item and target page
- No routing library; purely DOM manipulation

### Styling Conventions
- **Color scheme**: Dark sidebar (`#0d1b2a`), light backgrounds (`#f4f6f9`), cyan accent (`#4cc9f0`)
- **Components**: Reusable `.card` class (white background, 20px padding, box-shadow)
- **Font**: Outfit family for all text
- **Responsive**: Viewport meta tag present, mobile-friendly layout

### Module Sections (Not Yet Implemented)
- **Dashboard**: Summary cards (revenue, pending invoices)
- **Factures**: Invoice creation & list management
- **Comptabilité**: Moroccan accounting plan (Plan Comptable Marocain)
- **Clients**: Customer database
- **Produits**: Product/service catalog
- **Paramètres**: Company info (ICE, IF, RC, TVA numbers)

## When Extending This Project

### Adding New Features
1. Add `<section id="page-name" class="page">` in main-content
2. Add `.nav-item[data-page="page-name"]` in sidebar
3. JavaScript already handles event binding—no additional listeners needed
4. Follow existing card structure for consistent UI

### Integration Points to Prepare
- **Database**: Currently static/mock data; prepare for backend API calls in each page section
- **Forms**: Invoice and client forms will need validation logic
- **Accounting Logic**: Moroccan tax calculations (TVA), journal entries

### Style Extensions
- Maintain cyan (`#4cc9f0`) as primary action color
- Use dark sidebar theme for consistency
- All new cards should use `.card` class template

## File Location Note
Application is currently `index (2).html` (filename includes space and number). Consider renaming to `index.html` for clarity if restructuring.
