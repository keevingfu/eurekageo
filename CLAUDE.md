# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Eureka GEO Project Management System** is a comprehensive web-based platform for managing Generative Engine Optimization (GEO) strategies. The system monitors and optimizes brand visibility across AI platforms like ChatGPT, Perplexity, Gemini, and Claude, providing real-time analytics, competitive intelligence, and content optimization tools.

## Architecture & Technical Stack

### Frontend Architecture
- **Framework**: Vanilla HTML/CSS/JavaScript with ECharts v5.4.3 for data visualization
- **Design Pattern**: Self-contained HTML files with inline styles and scripts
- **Styling**: Custom CSS with modern design system (CSS variables, gradients, glassmorphism effects)
- **Charts**: ECharts for all data visualizations (line charts, bar charts, radar charts, etc.)
- **Language**: Chinese interface with some English technical terms

### Project Structure
```
geopm/
├── geo-pm.html                          # Main login and project management interface
├── eureka-geo-overview.html             # Analytics dashboard with dark theme
├── eureka-geo-system.html               # System monitoring dashboard
├── eureka-geo-phase[1-4].html          # Phase-specific dashboards
├── eureka-geo-phase[1-4]-report.html   # Phase-specific report generators
├── eureka-geo-phace1-*.html           # Phase 1 specific tools (diagnostic, baseline, etc.)
├── eureka-geo-phace2-*.html           # Phase 2 optimization tools
└── geo-des.html                        # Additional design/visualization page
```

### Key System Modules

1. **Project Management Module** (`geo-pm.html`)
   - Login system and authentication
   - Task management with kanban boards
   - Project phase tracking (4 phases: 基础诊断, 试点优化, 规模扩展, 持续优化)
   - Team collaboration features

2. **Analytics Dashboards** 
   - Real-time metrics visualization
   - Multi-platform performance tracking
   - Competitive analysis
   - Conversion funnel analysis

3. **Diagnostic Tools**
   - AI platform performance diagnostics
   - Brand mention monitoring
   - Content effectiveness analysis
   - Baseline establishment tools

4. **Content Optimization Tools**
   - E-E-A-T optimization modules
   - FAQ content generators
   - Schema markup tools
   - Content performance tracking

5. **Reporting System**
   - Automated report generation
   - Phase-specific insights
   - Export capabilities
   - Executive summaries

## Development Commands

This is a static HTML project with no build process. To work with the project:

```bash
# Open any HTML file directly in a browser
open eureka-geo-overview.html

# For local development with live reload (optional)
python -m http.server 8000
# or
npx http-server
```

## Data Visualization Standards

### Color Scheme
```css
--primary-color: #2563eb;    /* Blue */
--success-color: #22c55e;    /* Green */
--warning-color: #f59e0b;    /* Amber */
--danger-color: #ef4444;     /* Red */
--background: #f8fafc;       /* Light gray */
--text-primary: #1e293b;     /* Dark text */
```

### Chart Configuration
- All charts use ECharts v5.4.3 from CDN
- Chart initialization pattern:
```javascript
const chart = echarts.init(document.getElementById('chartId'));
const option = { /* chart configuration */ };
chart.setOption(option);
```

### Key Metrics Tracked
- **AI提及率 (AI Mention Rate)**: Brand mention percentage in AI responses
- **SoV-AI (Share of Voice)**: Brand's word count share in AI responses
- **引用分数 (Citation Score)**: Quality and authority of citations
- **转化率 (Conversion Rate)**: From AI mention to purchase conversion
- **平台覆盖率 (Platform Coverage)**: Brand presence across AI platforms

## Code Patterns & Conventions

### HTML Structure
- Each file is self-contained with inline CSS and JavaScript
- Consistent use of semantic HTML5 elements
- Mobile-responsive design using CSS Grid and Flexbox

### JavaScript Patterns
- Chart data is typically embedded as JavaScript objects
- Event handlers are added inline or via addEventListener
- No external JavaScript dependencies except ECharts

### CSS Architecture
- CSS variables for theming and consistency
- Responsive breakpoints for mobile compatibility
- Modern CSS features (gradients, backdrop-filter, transforms)

## Working with Charts

### Adding New Charts
1. Add a container div with unique ID
2. Initialize chart with `echarts.init()`
3. Configure options following existing patterns
4. Call `chart.setOption(option)`

### Updating Chart Data
- Modify the data arrays in chart options
- Call `chart.setOption()` with updated data
- Use `chart.resize()` for responsive behavior

## Important Considerations

1. **Language**: Interface is primarily in Chinese - maintain consistency in terminology
2. **Performance**: Keep inline data reasonable to avoid large file sizes
3. **Browser Compatibility**: Requires modern browsers with ES6 support
4. **Chart Performance**: Limit data points for smooth animations
5. **Mobile Support**: Test all interfaces on mobile devices
6. **Data Security**: No sensitive data should be hardcoded in HTML files

## Phase-Specific Features

### Phase 1 (基础诊断)
- Baseline establishment
- Initial diagnostics
- Data collection tools
- Competitive analysis setup

### Phase 2 (试点优化)
- E-E-A-T optimization
- Content improvement
- FAQ development
- A/B testing setup

### Phase 3 (规模扩展)
- Multi-platform expansion
- Automation implementation
- Scale optimization
- Performance monitoring

### Phase 4 (持续优化)
- Continuous monitoring
- Automated reporting
- Innovation testing
- ROI optimization

## Current Project Status (Updated: 2025-08-10)

### Completed Features
1. **Portal System** (`index.html`)
   - English-only navigation portal with left sidebar menu
   - iFrame-based content display system
   - Organized navigation structure with 4 phase sections
   - Welcome screen with feature overview

2. **Navigation Structure**
   - **Dashboard**: Design Showcase, System Monitor, Analytics Overview
   - **Phase 1**: Phase 1 Guide, Phase 1 Checklist, Data Collection, Baseline Analysis
   - **Phase 2**: FAQ Content, Comparison Analysis, E-E-A-T Optimization, Phase 2 Report
   - **Phase 3**: Phase 3 Dashboard, Phase 3 Report
   - **Phase 4**: Phase 4 Dashboard, Phase 4 Report

3. **Recent Updates**
   - Removed Project Management menu item from Dashboard
   - Reordered Dashboard menu items (Design Showcase first)
   - Streamlined Phase 1 menu to only 4 essential items
   - Reordered Phase 2 menu items with FAQ Content first
   - Added brand logos to comparison table (Eureka, Roborock, iRobot, Ecovacs)
   - Removed "成功案例" section from geo-des.html
   - All navigation items verified to have corresponding HTML files

4. **Repository Status**
   - Git repository initialized and connected to GitHub
   - All files committed and pushed to https://github.com/keevingfu/eurekageo
   - Repository contains 26 files including all HTML pages and documentation

### File Inventory
- 24 HTML files (including index.html portal)
- 2 Markdown documentation files (CLAUDE.md, Eureka GEO 项目管理系统.md)
- All files use Chinese interface with English navigation in portal

## Future Enhancements

The documentation suggests planned features for a full-stack implementation:
- React + Node.js architecture
- MongoDB for data persistence
- Real-time API integrations
- User authentication system
- Automated alert system
- Slack/email notifications

Currently, the project consists of static HTML demonstrations of the planned interface.