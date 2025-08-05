Based on the customer list and customer detail page requirements, here's the comprehensive API structure needed:

Required APIs
Customer Management APIs
1. GET /api/customers - Get paginated customers list
2. GET /api/customers/{customerId} - Get specific customer details
3. GET /api/customers/{customerId}/kpis - Get customer KPI metrics
4. GET /api/customers/{customerId}/alerts - Get customer alerts
Product & Service APIs
5. GET /api/customers/{customerId}/products - Get customer product solutions
6. GET /api/customers/{customerId}/commitments - Get contractual commitments
7. GET /api/customers/{customerId}/constraints - Get service constraints
Monitoring & Analytics APIs
8. GET /api/customers/{customerId}/sites - Get customer sites
9. GET /api/customers/{customerId}/monitoring - Get site-level monitoring data
10. GET /api/customers/{customerId}/timeseries - Get time-series chart data
Global APIs
11. GET /api/kpis/summary - Get global KPI summary
12. GET /api/notifications - Get system notifications
13. GET /api/updates - Get "What's New" updates



Mock API Responses
1. GET /api/customers
{
  "data": [
    {
      "id": "customer-022",
      "name": "Enterprise Corp",
      "status": "active",
      "tier": "enterprise",
      "connectionUsage": {
        "current": 528,
        "limit": 650,
        "percentage": 81.2
      },
      "alertCount": 3,
      "lastActivity": "2024-08-05T10:30:00Z",
      "kpis": {
        "revenue": 125000,
        "growth": 12.5,
        "satisfaction": 4.2
      }
    }
  ],
  "pagination": {
    "total": 156,
    "page": 1,
    "limit": 10,
    "totalPages": 16
  },
  "meta": {
    "timestamp": "2024-08-05T10:35:00Z"
  }
}

2. GET /api/customers/{customerId}
{
  "data": {
    "id": "customer-022",
    "name": "Enterprise Corp",
    "status": "active",
    "tier": "enterprise",
    "createdAt": "2023-01-15T09:00:00Z",
    "contact": {
      "email": "admin@enterprisecorp.com",
      "phone": "+1-555-0123"
    },
    "billing": {
      "plan": "Enterprise Premium",
      "billingCycle": "monthly",
      "nextBilling": "2024-09-01T00:00:00Z"
    }
  }
}

use below v0 preview link and create the same UI project in react.
https://preview-rate-limit-kpis-display-multi-cust-kzmpmzwxfi6qjuzsglle.vusercontent.net/
Lovable
Worked for 1m 6s
1:43 PM on Aug 05

Thought for 23 seconds
I'll fetch the website first to see what we're building, then create the same UI in React.

Fetched
https://preview-rate-limit-kpis-display-multi-cust-kzmpmzwxfi6qjuzsglle.vusercontent.net/
Perfect! I can see this is a customer dashboard with KPI monitoring. The design features:

Design Elements:

Clean, professional dashboard layout
Two main KPI cards (Total Customers: 547, Critical Alerts: 1680)
Search and filter functionality
Data table with customer information
Industry categories, subscription services, and alert counts
Modern card-based design with subtle shadows
Features to implement:

Dashboard header with title and description
KPI cards with icons and metrics
Search bar and filter dropdowns
Customer data table with industry categories
Alert badges with color coding
Let me create this dashboard with a professional blue/gray color scheme and modern design system:

Show all
Editing
tailwind.config.ts
This message was cancelled.



No need to create the react app, just create the detailed step by step task list which can be used to create the same UI project later.
Lovable
Worked for 41s
1:45 PM on Aug 05

Show all
2 tools used
Based on the website analysis, here's a detailed step-by-step task list to recreate the Customer Dashboard UI:

Phase 1: Project Setup & Design System
Initialize design system

Update src/index.css with professional blue/gray color scheme
Define semantic tokens for primary, secondary, muted colors
Add proper light/dark mode variables
Configure Tailwind

Extend color palette in tailwind.config.ts
Add custom spacing and typography scales
Phase 2: Core Components
Create KPI Card Component (src/components/KpiCard.tsx)

Display metric value and label
Support icon integration
Include variant for alert/warning states
Create Customer Table Component (src/components/CustomerTable.tsx)

Sortable columns (Customer, Active Subscriptions, Alerts)
Clickable customer names with links
Industry tags/badges
Alert count with color coding
Create Filter Components

Industry dropdown filter (src/components/IndustryFilter.tsx)
Status dropdown filter (src/components/StatusFilter.tsx)
Items per page selector (src/components/PageSizeSelector.tsx)
Phase 3: Layout & Main Dashboard
Create Dashboard Header (src/components/DashboardHeader.tsx)

Title and subtitle
Responsive layout
Create Search Bar (src/components/SearchBar.tsx)

Input with search icon
Placeholder text "Search customers..."
Create Filter Bar (src/components/FilterBar.tsx)

Combine all filter components
Show result count ("Showing 1-25 of 547 customers")
Phase 4: Data & State Management
Create Mock Data (src/data/mockCustomers.ts)

Customer objects with: id, name, industry, subscriptions, alerts
Industry types: Pharmaceutical, Retail, Automotive, Finance, Energy
Subscription types: Demand Forecasting, Inventory Analytics, etc.
Create Custom Hooks

src/hooks/useCustomerFilters.ts - Handle search, filter, pagination
src/hooks/useCustomerData.ts - Data fetching and state management
Phase 5: Main Dashboard Assembly
Update Index Page (src/pages/Index.tsx)
Implement full dashboard layout
Integrate all components
Add responsive grid for KPI cards
Wire up filtering and search functionality
Phase 6: Styling & Polish
Responsive Design

Mobile-first approach
Collapsible filters on small screens
Horizontal scroll for table on mobile
Accessibility

Proper ARIA labels
Keyboard navigation
Screen reader support
Loading States

Skeleton components for table rows
Loading states for filters
Phase 7: Advanced Features
Customer Detail Navigation

React Router setup for customer detail pages
Breadcrumb navigation
Data Export (Optional)

CSV export functionality
Print-friendly view
This task list provides a comprehensive roadmap to recreate the exact Customer Dashboard UI with proper component architecture and modern React patterns.




now let's create the same step by step tasks list for the customer detail page which lists multiple products, refer below v0 link for reference of UI.
https://preview-rate-limit-kpis-display-multi-cust-kzmpmzwxfi6qjuzsglle.vusercontent.net/customer/customer-022
now let's create the same step by step tasks list for the customer detail page which lists multiple products, refer below v0 link for reference of UI.
https://preview-rate-limit-kpis-display-multi-cust-kzmpmzwxfi6qjuzsglle.vusercontent.net/customer/customer-022
Lovable
Worked for 1m 28s
1:54 PM on Aug 05

Show all
2 tools used
Based on the customer detail page UI, here's a comprehensive step-by-step task list to recreate the Customer Detail Dashboard:

Customer Detail Page - Step-by-Step Task List
Phase 1: Project Setup & Route Configuration
Add Customer Detail Route

Add /customer/:customerId route to App.tsx
Create CustomerDetail page component
Update Navigation

Add breadcrumb navigation (Customers / Customer 022)
Ensure clickable navigation back to customers list
Phase 2: Page Header & Meta Information
Create Page Header Component

Customer ID display (customer 022)
Page title with subtitle
Export Data button with icon
Notification bell with badge count
Create Alert Banner Component

Warning/info banner for KPI status
Dismissible banner with close button
Dynamic content based on alert count
Phase 3: What's New Section
Create Updates Card Component

Collapsible "What's New" section
Update counter badge
Individual update items with status badges (NEW, UPDATED, BETA)
Create Update Item Component

Icon + title + status badge
Description text
Action button (Learn More, Explore, Try Beta)
Phase 4: KPI Overview Cards
Create Global KPI Card
Current month selector dropdown
Connection usage display (528/650)
Progress bar visualization
"Buy more" action button
Phase 5: Product Solutions Section
Create Product Solution Card

Collapsible/expandable product cards
Product header with metrics summary
Alert count badge
Quick stats display
Create Contractual Commitments Section

Section title with description
Multiple commitment items
Progress bars for usage metrics
Individual "Buy more" buttons
Create Service Constraints Section

Enterprise level constraints
Individual metric cards with usage bars
Color-coded progress indicators
Phase 6: Site-Level Monitoring
Create Site Filter Component

Multi-select dropdown for sites
Selected count display
SLA violations toggle with count
Create Time-Series Chart Components

Multiple small chart components
24-hour timeline (01:00 - 23:00)
Different chart types (line, bar)
Violation indicators
Responsive chart sizing
Phase 7: Data Management & State
Create Customer Data Hook

Fetch customer details by ID
Product solutions data
KPI metrics and alerts
Site-level monitoring data
Create Chart Data Hook

Time-series data formatting
Chart configuration
Real-time data updates
Phase 8: Interactive Features
Implement Collapsible Sections

Expand/collapse animations
State persistence
Smooth transitions
Add Progress Bar Components

Different sizes and variants
Color coding (warning, danger, success)
Animated progress indicators
Phase 9: Advanced Components
Create Metric Cards

Reusable metric display component
Usage/limit formatting
Status indicators
Action buttons
Create Time Selector

Dropdown for time periods
Calendar integration option
Date range selection
Phase 10: Responsive Design & Polish
Mobile Responsiveness

Responsive chart layouts
Mobile-friendly navigation
Touch-friendly interactions
Collapsible sections on mobile
Accessibility Features

ARIA labels for charts
Keyboard navigation
Screen reader support
Color contrast compliance
Phase 11: Performance Optimization
Chart Performance

Lazy loading for charts
Data virtualization
Debounced interactions
Memoized components
Data Loading States

Skeleton loaders for charts
Progressive data loading
Error boundaries
Retry mechanisms
Phase 12: Additional Features
Export Functionality

Data export options
Multiple format support
Progress indicators
Download notifications
Real-time Updates

WebSocket integration
Live KPI updates
Alert notifications
Auto-refresh intervals
This task list provides a comprehensive roadmap to recreate the customer detail page with all its interactive features, charts, and responsive design elements.




create the list of APIs required for above both the requirements, and also create a mock response to finalise the backend API response structure.
create the list of APIs required for above both the requirements, and also create a mock response to finalise the backend API response structure.
Lovable
Worked for 36s
2:12 PM on Aug 05

Thought for 9 seconds
Based on the customer list and customer detail page requirements, here's the comprehensive API structure needed:

Required APIs
Customer Management APIs
GET /api/customers - Get paginated customers list
GET /api/customers/{customerId} - Get specific customer details
GET /api/customers/{customerId}/kpis - Get customer KPI metrics
GET /api/customers/{customerId}/alerts - Get customer alerts
Product & Service APIs
GET /api/customers/{customerId}/products - Get customer product solutions
GET /api/customers/{customerId}/commitments - Get contractual commitments
GET /api/customers/{customerId}/constraints - Get service constraints
Monitoring & Analytics APIs
GET /api/customers/{customerId}/sites - Get customer sites
GET /api/customers/{customerId}/monitoring - Get site-level monitoring data
GET /api/customers/{customerId}/timeseries - Get time-series chart data
Global APIs
GET /api/kpis/summary - Get global KPI summary
GET /api/notifications - Get system notifications
GET /api/updates - Get "What's New" updates
Mock API Responses
1. GET /api/customers

{
  "data": [
    {
      "id": "customer-022",
      "name": "Enterprise Corp",
      "status": "active",
      "tier": "enterprise",
      "connectionUsage": {
        "current": 528,
        "limit": 650,
        "percentage": 81.2
      },
      "alertCount": 3,
      "lastActivity": "2024-08-05T10:30:00Z",
      "kpis": {
        "revenue": 125000,
        "growth": 12.5,
        "satisfaction": 4.2
      }
    }
  ],
  "pagination": {
    "total": 156,
    "page": 1,
    "limit": 10,
    "totalPages": 16
  },
  "meta": {
    "timestamp": "2024-08-05T10:35:00Z"
  }
}
2. GET /api/customers/{customerId}

{
  "data": {
    "id": "customer-022",
    "name": "Enterprise Corp",
    "status": "active",
    "tier": "enterprise",
    "createdAt": "2023-01-15T09:00:00Z",
    "contact": {
      "email": "admin@enterprisecorp.com",
      "phone": "+1-555-0123"
    },
    "billing": {
      "plan": "Enterprise Premium",
      "billingCycle": "monthly",
      "nextBilling": "2024-09-01T00:00:00Z"
    }
  }
}
3. GET /api/customers/{customerId}/kpis

{
  "data": {
    "connectionUsage": {
      "current": 528,
      "limit": 650,
      "percentage": 81.2,
      "trend": "increasing"
    },
    "performance": {
      "uptime": 99.8,
      "responseTime": 245,
      "errorRate": 0.02
    },
    "financial": {
      "revenue": 125000,
      "growth": 12.5,
      "arr": 1500000
    }
  },
  "period": "2024-08",
  "lastUpdated": "2024-08-05T10:30:00Z"
}
4. GET /api/customers/{customerId}/products

{
  "data": [
    {
      "id": "prod-api-gateway",
      "name": "API Gateway Enterprise",
      "status": "active",
      "alertCount": 2,
      "metrics": {
        "requests": 2500000,
        "uptime": 99.9,
        "latency": 120
      },
      "commitment": {
        "type": "requests",
        "used": 2500000,
        "limit": 5000000,
        "percentage": 50
      }
    },
    {
      "id": "prod-data-sync",
      "name": "Data Synchronization",
      "status": "warning",
      "alertCount": 1,
      "metrics": {
        "syncJobs": 1250,
        "successRate": 98.5,
        "dataVolume": "2.5TB"
      }
    }
  ]
}
5. GET /api/customers/{customerId}/timeseries

{
  "data": {
    "connectionUsage": [
      {
        "timestamp": "2024-08-05T01:00:00Z",
        "value": 420,
        "violations": 0
      },
      {
        "timestamp": "2024-08-05T02:00:00Z",
        "value": 385,
        "violations": 0
      },
      {
        "timestamp": "2024-08-05T03:00:00Z",
        "value": 445,
        "violations": 1
      }
    ],
    "responseTime": [
      {
        "timestamp": "2024-08-05T01:00:00Z",
        "average": 245,
        "p95": 480,
        "p99": 720
      }
    ],
    "errorRate": [
      {
        "timestamp": "2024-08-05T01:00:00Z",
        "rate": 0.02,
        "count": 15
      }
    ]
  },
  "timeRange": {
    "start": "2024-08-05T00:00:00Z",
    "end": "2024-08-05T23:59:59Z",
    "granularity": "hourly"
  }
}
6. GET /api/customers/{customerId}/alerts

{
  "data": [
    {
      "id": "alert-001",
      "type": "warning",
      "severity": "medium",
      "title": "Connection usage approaching limit",
      "description": "Customer is at 81% of connection limit",
      "timestamp": "2024-08-05T09:45:00Z",
      "resolved": false,
      "product": "API Gateway Enterprise"
    },
    {
      "id": "alert-002",
      "type": "error",
      "severity": "high",
      "title": "SLA violation detected",
      "description": "Response time exceeded SLA threshold",
      "timestamp": "2024-08-05T08:30:00Z",
      "resolved": false,
      "product": "Data Synchronization"
    }
  ],
  "summary": {
    "total": 3,
    "critical": 0,
    "high": 1,
    "medium": 2,
    "low": 0
  }
}
7. GET /api/updates

{
  "data": [
    {
      "id": "update-001",
      "title": "Enhanced API Analytics",
      "description": "New detailed analytics dashboard with real-time insights",
      "status": "NEW",
      "category": "feature",
      "releaseDate": "2024-08-01T00:00:00Z",
      "action": {
        "text": "Learn More",
        "url": "/features/analytics"
      }
    },
    {
      "id": "update-002",
      "title": "Beta: AI-Powered Alerting",
      "description": "Intelligent alert system using machine learning",
      "status": "BETA",
      "category": "beta",
      "releaseDate": "2024-07-28T00:00:00Z",
      "action": {
        "text": "Try Beta",
        "url": "/beta/ai-alerts"
      }
    }
  ],
  "count": 4
}
This API structure provides comprehensive data for both customer list and detail pages with proper pagination, filtering, and real-time monitoring capabilities.




looks like for few endpoints sample mock response is missing.
Lovable
Worked for 38s
2:17 PM on Aug 05

Thought for 10 seconds
You're absolutely right! Here are the missing mock responses for the remaining endpoints:

Missing Mock API Responses
8. GET /api/customers/{customerId}/commitments

{
  "data": [
    {
      "id": "commit-001",
      "type": "API Calls",
      "description": "Monthly API call allocation",
      "used": 2500000,
      "limit": 5000000,
      "percentage": 50,
      "unit": "calls",
      "resetDate": "2024-09-01T00:00:00Z",
      "status": "healthy"
    },
    {
      "id": "commit-002", 
      "type": "Data Transfer",
      "description": "Monthly data transfer limit",
      "used": 2.5,
      "limit": 10,
      "percentage": 25,
      "unit": "TB",
      "resetDate": "2024-09-01T00:00:00Z",
      "status": "healthy"
    },
    {
      "id": "commit-003",
      "type": "Concurrent Connections",
      "description": "Maximum simultaneous connections",
      "used": 528,
      "limit": 650,
      "percentage": 81.2,
      "unit": "connections",
      "status": "warning"
    }
  ]
}
9. GET /api/customers/{customerId}/constraints

{
  "data": [
    {
      "id": "constraint-001",
      "level": "Enterprise",
      "category": "Performance",
      "metrics": [
        {
          "name": "Response Time SLA",
          "current": 245,
          "threshold": 500,
          "unit": "ms",
          "status": "healthy",
          "percentage": 49
        },
        {
          "name": "Uptime SLA",
          "current": 99.8,
          "threshold": 99.5,
          "unit": "%",
          "status": "healthy",
          "percentage": 100
        },
        {
          "name": "Error Rate",
          "current": 0.02,
          "threshold": 0.1,
          "unit": "%",
          "status": "healthy",
          "percentage": 20
        }
      ]
    },
    {
      "id": "constraint-002",
      "level": "Enterprise",
      "category": "Security",
      "metrics": [
        {
          "name": "Failed Auth Attempts",
          "current": 5,
          "threshold": 100,
          "unit": "attempts/hour",
          "status": "healthy",
          "percentage": 5
        }
      ]
    }
  ]
}
10. GET /api/customers/{customerId}/sites

{
  "data": [
    {
      "id": "site-us-east-1",
      "name": "US East (Virginia)",
      "region": "us-east-1",
      "status": "active",
      "slaViolations": 2,
      "lastViolation": "2024-08-05T08:30:00Z",
      "metrics": {
        "uptime": 99.8,
        "responseTime": 120,
        "throughput": 15000
      }
    },
    {
      "id": "site-eu-west-1", 
      "name": "EU West (Ireland)",
      "region": "eu-west-1",
      "status": "active",
      "slaViolations": 0,
      "lastViolation": null,
      "metrics": {
        "uptime": 99.9,
        "responseTime": 95,
        "throughput": 8500
      }
    },
    {
      "id": "site-ap-southeast-1",
      "name": "Asia Pacific (Singapore)", 
      "region": "ap-southeast-1",
      "status": "warning",
      "slaViolations": 1,
      "lastViolation": "2024-08-05T06:15:00Z",
      "metrics": {
        "uptime": 99.7,
        "responseTime": 180,
        "throughput": 5200
      }
    }
  ],
  "summary": {
    "totalSites": 3,
    "activeSites": 3,
    "totalViolations": 3,
    "avgUptime": 99.8
  }
}
11. GET /api/customers/{customerId}/monitoring

{
  "data": {
    "realTimeMetrics": {
      "activeConnections": 528,
      "requestsPerSecond": 1250,
      "avgResponseTime": 245,
      "errorRate": 0.02
    },
    "siteStatus": [
      {
        "siteId": "site-us-east-1",
        "status": "healthy",
        "responseTime": 120,
        "uptime": 99.8,
        "violations": []
      },
      {
        "siteId": "site-ap-southeast-1", 
        "status": "degraded",
        "responseTime": 580,
        "uptime": 99.7,
        "violations": [
          {
            "type": "response_time",
            "threshold": 500,
            "actual": 580,
            "timestamp": "2024-08-05T06:15:00Z"
          }
        ]
      }
    ],
    "alerts": {
      "active": 3,
      "resolved": 12,
      "lastAlert": "2024-08-05T09:45:00Z"
    }
  },
  "lastUpdated": "2024-08-05T10:35:00Z"
}
12. GET /api/kpis/summary

{
  "data": {
    "global": {
      "totalCustomers": 156,
      "activeCustomers": 148,
      "totalRevenue": 15750000,
      "growthRate": 18.5,
      "avgSatisfaction": 4.3
    },
    "platform": {
      "totalRequests": 250000000,
      "avgResponseTime": 180,
      "uptime": 99.9,
      "errorRate": 0.01
    },
    "alerts": {
      "critical": 2,
      "high": 8,
      "medium": 24,
      "low": 15,
      "total": 49
    },
    "capacity": {
      "connectionUtilization": 78.5,
      "storageUtilization": 65.2,
      "computeUtilization": 82.1
    }
  },
  "period": "2024-08",
  "lastUpdated": "2024-08-05T10:35:00Z"
}
13. GET /api/notifications

{
  "data": [
    {
      "id": "notif-001",
      "type": "system",
      "severity": "info",
      "title": "Scheduled Maintenance",
      "message": "System maintenance scheduled for Aug 10, 2024 from 2:00-4:00 AM UTC",
      "timestamp": "2024-08-05T09:00:00Z",
      "read": false,
      "actions": [
        {
          "text": "View Details",
          "url": "/maintenance/schedule"
        }
      ]
    },
    {
      "id": "notif-002",
      "type": "alert",
      "severity": "warning", 
      "title": "High API Usage Detected",
      "message": "Multiple customers approaching rate limits",
      "timestamp": "2024-08-05T08:45:00Z",
      "read": false,
      "actions": [
        {
          "text": "View Report",
          "url": "/reports/usage"
        }
      ]
    },
    {
      "id": "notif-003",
      "type": "feature",
      "severity": "info",
      "title": "New Feature Available",
      "message": "Enhanced analytics dashboard is now live",
      "timestamp": "2024-08-04T14:30:00Z", 
      "read": true,
      "actions": [
        {
          "text": "Explore",
          "url": "/features/analytics"
        }
      ]
    }
  ],
  "summary": {
    "total": 12,
    "unread": 8,
    "critical": 0,
    "warnings": 3
  }
}

8. GET /api/customers/{customerId}/commitments

{
  "data": [
    {
      "id": "commit-001",
      "type": "API Calls",
      "description": "Monthly API call allocation",
      "used": 2500000,
      "limit": 5000000,
      "percentage": 50,
      "unit": "calls",
      "resetDate": "2024-09-01T00:00:00Z",
      "status": "healthy"
    },
    {
      "id": "commit-002", 
      "type": "Data Transfer",
      "description": "Monthly data transfer limit",
      "used": 2.5,
      "limit": 10,
      "percentage": 25,
      "unit": "TB",
      "resetDate": "2024-09-01T00:00:00Z",
      "status": "healthy"
    },
    {
      "id": "commit-003",
      "type": "Concurrent Connections",
      "description": "Maximum simultaneous connections",
      "used": 528,
      "limit": 650,
      "percentage": 81.2,
      "unit": "connections",
      "status": "warning"
    }
  ]
}

9. GET /api/customers/{customerId}/constraints

{
  "data": [
    {
      "id": "constraint-001",
      "level": "Enterprise",
      "category": "Performance",
      "metrics": [
        {
          "name": "Response Time SLA",
          "current": 245,
          "threshold": 500,
          "unit": "ms",
          "status": "healthy",
          "percentage": 49
        },
        {
          "name": "Uptime SLA",
          "current": 99.8,
          "threshold": 99.5,
          "unit": "%",
          "status": "healthy",
          "percentage": 100
        },
        {
          "name": "Error Rate",
          "current": 0.02,
          "threshold": 0.1,
          "unit": "%",
          "status": "healthy",
          "percentage": 20
        }
      ]
    },
    {
      "id": "constraint-002",
      "level": "Enterprise",
      "category": "Security",
      "metrics": [
        {
          "name": "Failed Auth Attempts",
          "current": 5,
          "threshold": 100,
          "unit": "attempts/hour",
          "status": "healthy",
          "percentage": 5
        }
      ]
    }
  ]
}

10. GET /api/customers/{customerId}/sites

{
  "data": [
    {
      "id": "site-us-east-1",
      "name": "US East (Virginia)",
      "region": "us-east-1",
      "status": "active",
      "slaViolations": 2,
      "lastViolation": "2024-08-05T08:30:00Z",
      "metrics": {
        "uptime": 99.8,
        "responseTime": 120,
        "throughput": 15000
      }
    },
    {
      "id": "site-eu-west-1", 
      "name": "EU West (Ireland)",
      "region": "eu-west-1",
      "status": "active",
      "slaViolations": 0,
      "lastViolation": null,
      "metrics": {
        "uptime": 99.9,
        "responseTime": 95,
        "throughput": 8500
      }
    },
    {
      "id": "site-ap-southeast-1",
      "name": "Asia Pacific (Singapore)", 
      "region": "ap-southeast-1",
      "status": "warning",
      "slaViolations": 1,
      "lastViolation": "2024-08-05T06:15:00Z",
      "metrics": {
        "uptime": 99.7,
        "responseTime": 180,
        "throughput": 5200
      }
    }
  ],
  "summary": {
    "totalSites": 3,
    "activeSites": 3,
    "totalViolations": 3,
    "avgUptime": 99.8
  }
}

11. GET /api/customers/{customerId}/monitoring

{
  "data": {
    "realTimeMetrics": {
      "activeConnections": 528,
      "requestsPerSecond": 1250,
      "avgResponseTime": 245,
      "errorRate": 0.02
    },
    "siteStatus": [
      {
        "siteId": "site-us-east-1",
        "status": "healthy",
        "responseTime": 120,
        "uptime": 99.8,
        "violations": []
      },
      {
        "siteId": "site-ap-southeast-1", 
        "status": "degraded",
        "responseTime": 580,
        "uptime": 99.7,
        "violations": [
          {
            "type": "response_time",
            "threshold": 500,
            "actual": 580,
            "timestamp": "2024-08-05T06:15:00Z"
          }
        ]
      }
    ],
    "alerts": {
      "active": 3,
      "resolved": 12,
      "lastAlert": "2024-08-05T09:45:00Z"
    }
  },
  "lastUpdated": "2024-08-05T10:35:00Z"
}

12. GET /api/kpis/summary

{
  "data": {
    "global": {
      "totalCustomers": 156,
      "activeCustomers": 148,
      "totalRevenue": 15750000,
      "growthRate": 18.5,
      "avgSatisfaction": 4.3
    },
    "platform": {
      "totalRequests": 250000000,
      "avgResponseTime": 180,
      "uptime": 99.9,
      "errorRate": 0.01
    },
    "alerts": {
      "critical": 2,
      "high": 8,
      "medium": 24,
      "low": 15,
      "total": 49
    },
    "capacity": {
      "connectionUtilization": 78.5,
      "storageUtilization": 65.2,
      "computeUtilization": 82.1
    }
  },
  "period": "2024-08",
  "lastUpdated": "2024-08-05T10:35:00Z"
}

13. GET /api/notifications

{
  "data": [
    {
      "id": "notif-001",
      "type": "system",
      "severity": "info",
      "title": "Scheduled Maintenance",
      "message": "System maintenance scheduled for Aug 10, 2024 from 2:00-4:00 AM UTC",
      "timestamp": "2024-08-05T09:00:00Z",
      "read": false,
      "actions": [
        {
          "text": "View Details",
          "url": "/maintenance/schedule"
        }
      ]
    },
    {
      "id": "notif-002",
      "type": "alert",
      "severity": "warning", 
      "title": "High API Usage Detected",
      "message": "Multiple customers approaching rate limits",
      "timestamp": "2024-08-05T08:45:00Z",
      "read": false,
      "actions": [
        {
          "text": "View Report",
          "url": "/reports/usage"
        }
      ]
    },
    {
      "id": "notif-003",
      "type": "feature",
      "severity": "info",
      "title": "New Feature Available",
      "message": "Enhanced analytics dashboard is now live",
      "timestamp": "2024-08-04T14:30:00Z", 
      "read": true,
      "actions": [
        {
          "text": "Explore",
          "url": "/features/analytics"
        }
      ]
    }
  ],
  "summary": {
    "total": 12,
    "unread": 8,
    "critical": 0,
    "warnings": 3
  }
}