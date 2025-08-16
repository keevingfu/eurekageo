# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Eureka GEO Project Management System** is a comprehensive web-based platform for managing Generative Engine Optimization (GEO) strategies. The system monitors and optimizes brand visibility across AI platforms like ChatGPT, Perplexity, Gemini, and Claude, providing real-time analytics, competitive intelligence, and content optimization tools.

## Development Commands

This is a static HTML project with no build process. To work with the project:

```bash
# Open any HTML file directly in a browser
open index.html  # Opens the main portal

# For local development with live reload (optional)
python -m http.server 8000
# or
npx http-server

# Validate HTML syntax (if needed)
# Note: No linting or build commands exist for this static project
```

## Architecture Overview

This is a **static HTML demonstration** of the Eureka GEO system. Each HTML file is self-contained with inline CSS and JavaScript, requiring no build process or external dependencies except for ECharts CDN.

### Technical Stack
- **Frontend**: Vanilla HTML/CSS/JavaScript
- **Charts**: ECharts v5.4.3 (loaded from CDN)
- **Portal**: iFrame-based navigation system (`index.html`)
- **Language**: Chinese interface with English navigation in portal
- **Styling**: Modern CSS with variables, gradients, glassmorphism effects

### High-Level Architecture

The system follows a 4-phase GEO optimization methodology, with each phase having dedicated tools and dashboards:

1. **Portal System** (`index.html`)
   - Central navigation hub with left sidebar menu
   - iFrame-based content loading system
   - All other pages are loaded within this portal frame
   - Navigation items trigger `loadPage()` function to update iFrame src

2. **Phase-Based Organization**
   - **Phase 1 (基础诊断)**: Baseline establishment and diagnostics
   - **Phase 2 (试点优化)**: Content optimization and E-E-A-T improvements
   - **Phase 3 (规模扩展)**: Scaling and multi-platform expansion
   - **Phase 4 (持续优化)**: Continuous monitoring and ROI optimization

3. **Key Architectural Patterns**
   - Each HTML file contains all required CSS/JS inline (no external files)
   - Chart data is embedded as JavaScript objects (no API calls)
   - Responsive design using CSS Grid and Flexbox
   - Consistent color scheme and design language across all pages
   - No external dependencies except ECharts CDN (v5.4.3)


## Working with Charts and Data

### ECharts Integration
All data visualizations use ECharts v5.4.3 loaded from CDN. Charts are initialized with embedded data (no external API calls).

```javascript
// Standard chart initialization pattern
const chart = echarts.init(document.getElementById('chartId'));
const option = {
    // Chart configuration with inline data
    series: [{
        data: [/* embedded data points */]
    }]
};
chart.setOption(option);

// Responsive handling
window.addEventListener('resize', () => chart.resize());
```

### Key GEO Metrics
The system tracks these core metrics across AI platforms:
- **AI提及率 (AI Mention Rate)**: % of queries where brand is mentioned
- **SoV-AI (Share of Voice)**: Brand's word count share in AI responses
- **引用分数 (Citation Score)**: Weighted score of citation quality/authority
- **转化率 (Conversion Rate)**: AI mention → purchase conversion rate
- **平台覆盖率 (Platform Coverage)**: Brand presence across different AI platforms

## Code Patterns & Conventions

### Working with the Portal System
The `index.html` portal uses iFrame navigation. When adding new pages:
1. Create self-contained HTML file with all CSS/JS inline
2. Add navigation item to appropriate section in `index.html`
3. Ensure the page works correctly within the iFrame context

### Adding New Visualizations
When creating new charts or dashboards:
```javascript
// 1. Create container with unique ID
<div id="myChart" style="width: 100%; height: 400px;"></div>

// 2. Initialize after DOM ready
document.addEventListener('DOMContentLoaded', function() {
    const chart = echarts.init(document.getElementById('myChart'));
    
    // 3. Use consistent option structure
    const option = {
        title: { text: '图表标题' },
        tooltip: { trigger: 'axis' },
        series: [{ 
            type: 'line',  // or 'bar', 'pie', etc.
            data: [/* your data */]
        }]
    };
    
    chart.setOption(option);
});
```

### CSS Design System
All pages use consistent CSS variables defined in each file:
```css
:root {
    --primary-color: #2563eb;
    --success-color: #22c55e;
    --warning-color: #f59e0b;
    --danger-color: #ef4444;
    --background: #f8fafc;
    --text-primary: #1e293b;
}
```

## Navigation Structure

The portal system (`index.html`) provides organized access to all system features:

- **Dashboard Section**
  - Design Showcase (`geo-des.html`)
  - System Monitor (`eureka-geo-system.html`)
  - Analytics Overview (`eureka-geo-overview.html`)

- **Strategy & Analysis** (New Section)
  - Market Opportunity (`01-eureka-geo-opportunity.html`)
  - GEO Strategy (`02-eureka-geo-strategy.html`)
  - 3-Step Methodology (`eureka-geo-optimization-strategy.html`)
  - Strategy Dashboard (`eureka-geo-strategy-dashboard.html`)

- **AI Channel Analysis** (New Section)
  - Channel Dashboard (`eureka-ai-channel-dashboard.html`)
  - Channel Diagnostic (`eureka-ai-channel-diagnostic.html`)

- **Phase 1 - 基础诊断 (Foundation & Diagnosis)**
  - Phase 1 Guide (`eureka-geo-phase1-guide.html`)
  - Phase 1 Checklist (`eureka-geo-phace1-checklist.html`)
  - Data Collection (`eureka-geo-phace1-datacollection.html`)
  - Baseline Analysis (`eureka-geo-phase1-baseline02.html`)
  - Tactical Execution Plan (`eureka-geo-implementation-guide.html`)
  - GEO Asset Library (`eureka-geo-dam.html`)

- **Phase 2 - 试点优化 (Pilot Optimization)**
  - FAQ Content (`eureka-geo-phace2-faq-content.html`)
  - Comparison Analysis (`eureka-geo-phace2-comparison.html`)
  - E-E-A-T Optimization (`eureka-geo-phace2-eeat-optimization.html`)
  - Phase 2 Report (`eureka-geo-phase2-report.html`)

- **Phase 3 & 4 - Scale & Continuous Optimization**
  - Phase dashboards and reports for scaling and ongoing optimization

## Important Notes

1. **Language**: All content pages use Chinese interface. Only the portal navigation is in English.
2. **File Naming**: Note the inconsistent spelling "phace" vs "phase" in filenames - maintain existing names to avoid breaking links.
3. **No Build Process**: This is a static demonstration. Simply open files in a browser.
4. **Repository**: https://github.com/keevingfu/eurekageo
5. **Future Architecture**: The Chinese documentation (`Eureka GEO 项目管理系统.md`) describes a planned full-stack implementation with React + Node.js + MongoDB + Redis, but the current implementation is static HTML only.

## Current Project Status (Updated: 2025-01-16)

### Recent Updates
1. **Navigation Categories in index.html**:
   - **Strategy & Analysis**: Market Opportunity, GEO Strategy, 3-Step Methodology, and Strategy Dashboard
   - **AI Channel Analysis**: Channel Dashboard and Channel Diagnostic

2. **Key Pages**:
   - `01-eureka-geo-opportunity.html` - US Market GEO Opportunity Dashboard
   - `02-eureka-geo-strategy.html` - GEO Optimization Strategy Dashboard  
   - `eureka-geo-optimization-strategy.html` - 3-Step Methodology
   - `eureka-geo-strategy-dashboard.html` - Strategy Dashboard
   - `eureka-ai-channel-dashboard.html` - AI Search Channel Analysis
   - `eureka-ai-channel-diagnostic.html` - AI Search Results Channel Diagnostic
   - `eureka-geo-implementation-guide.html` - Tactical Execution Plan (Phase 1)
   - `eureka-geo-dam.html` - GEO Asset Library visualization (Phase 1)

### File Inventory
- 31 HTML files (all self-contained with inline CSS/JS)
- 2 Markdown documentation files (CLAUDE.md, Eureka GEO 项目管理系统.md)
- All files are static - no compilation or build required

### Recent Git Activity
- Latest commit: Update CLAUDE.md with current project status
- 8 new HTML files added for Strategy & AI Channel features
- No configuration files or build tools present