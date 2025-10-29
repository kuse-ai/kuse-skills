---
name: backstage-style-web
description: Generate enterprise-grade web applications using Backstage Design System. Create admin dashboards, developer tools, and internal applications with modern React components, dark/light themes, and responsive design patterns based on Radix UI and Tailwind CSS.
---

# Backstage Style Web Generator

## Overview

Create professional, enterprise-grade web applications using the Backstage Design System. This skill generates modern React applications with TypeScript, featuring comprehensive UI components, dark/light theme support, responsive design, and accessibility-first patterns. Perfect for building admin dashboards, developer tools, internal applications, and data management interfaces.

## Core Design Philosophy

### 1. **Enterprise-Grade Quality**
- Production-ready component library with 47+ components
- Built on Radix UI primitives for accessibility
- Type-safe with TypeScript throughout
- Comprehensive theme system with light/dark modes

### 2. **Developer Experience First**
- Consistent API patterns across all components
- Class Variance Authority (CVA) for type-safe styling
- Tailwind CSS for utility-first styling
- React Hook Form integration for complex forms

### 3. **Accessibility & Responsiveness**
- ARIA attributes and keyboard navigation
- Mobile-first responsive design
- Screen reader compatibility
- Focus management and state indicators

## Application Types & Use Cases

### 1. Admin Dashboards
**Components**: Sidebar, DataTable, Cards, Forms, Charts
**Features**:
- Complex navigation with collapsible sidebar
- Data visualization and management
- User management and permissions
- Real-time updates and notifications

**Example Structure**:
```
Dashboard Layout:
├── Sidebar Navigation (collapsible)
├── Header (breadcrumbs, user menu)
├── Main Content Area
│   ├── Summary Cards
│   ├── Data Tables
│   └── Charts/Analytics
└── Footer
```

### 2. Developer Tools & Internal Apps
**Components**: Code blocks, Forms, Modals, Tooltips
**Features**:
- API documentation interfaces
- Configuration management
- Build and deployment tools
- Team collaboration features

### 3. Data Management Applications
**Components**: Tables, Filters, Search, Pagination
**Features**:
- CRUD operations with forms
- Advanced filtering and sorting
- Bulk operations
- Export functionality

### 4. Content Management Systems
**Components**: Rich text editors, Media uploads, Workflows
**Features**:
- Content creation and editing
- Workflow management
- User roles and permissions
- Publishing controls

## Component Architecture & Patterns

### 1. **Layout Components**
```typescript
// Sidebar with mobile responsiveness
<SidebarProvider defaultOpen={true}>
  <Sidebar>
    <SidebarHeader>
      <SidebarTitle>Application Name</SidebarTitle>
    </SidebarHeader>
    <SidebarContent>
      <SidebarGroup>
        <SidebarGroupContent>
          <SidebarMenu>
            <SidebarMenuItem>
              <SidebarMenuButton asChild>
                <a href="/dashboard">Dashboard</a>
              </SidebarMenuButton>
            </SidebarMenuItem>
          </SidebarMenu>
        </SidebarGroupContent>
      </SidebarGroup>
    </SidebarContent>
  </Sidebar>
  <main className="flex-1">
    {/* Main content */}
  </main>
</SidebarProvider>
```

### 2. **Data Display Pattern**
```typescript
// Card-based information display
<Card>
  <CardHeader>
    <CardTitle>Analytics Overview</CardTitle>
    <CardDescription>Key metrics for the past 30 days</CardDescription>
    <CardAction>
      <Button variant="outline" size="sm">
        <MoreHorizontal className="h-4 w-4" />
      </Button>
    </CardAction>
  </CardHeader>
  <CardContent>
    <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
      {/* Metrics */}
    </div>
  </CardContent>
</Card>
```

### 3. **Form Pattern with Validation**
```typescript
// Complete form with React Hook Form integration
<Form {...form}>
  <form onSubmit={form.handleSubmit(onSubmit)} className="space-y-6">
    <FormField
      control={form.control}
      name="username"
      render={({ field }) => (
        <FormItem>
          <FormLabel>Username</FormLabel>
          <FormControl>
            <Input placeholder="Enter username" {...field} />
          </FormControl>
          <FormDescription>
            This will be your public display name.
          </FormDescription>
          <FormMessage />
        </FormItem>
      )}
    />
    <Button type="submit">Submit</Button>
  </form>
</Form>
```

### 4. **Data Table Pattern**
```typescript
// Responsive data table with actions
<div className="rounded-md border">
  <Table>
    <TableHeader>
      <TableRow>
        <TableHead>Name</TableHead>
        <TableHead>Status</TableHead>
        <TableHead>Actions</TableHead>
      </TableRow>
    </TableHeader>
    <TableBody>
      {data.map((item) => (
        <TableRow key={item.id}>
          <TableCell>{item.name}</TableCell>
          <TableCell>
            <Badge variant={item.status === 'active' ? 'default' : 'secondary'}>
              {item.status}
            </Badge>
          </TableCell>
          <TableCell>
            <DropdownMenu>
              <DropdownMenuTrigger asChild>
                <Button variant="ghost" size="sm">
                  <MoreHorizontal className="h-4 w-4" />
                </Button>
              </DropdownMenuTrigger>
              <DropdownMenuContent>
                <DropdownMenuItem>Edit</DropdownMenuItem>
                <DropdownMenuItem>Delete</DropdownMenuItem>
              </DropdownMenuContent>
            </DropdownMenu>
          </TableCell>
        </TableRow>
      ))}
    </TableBody>
  </Table>
</div>
```

## Theme System & Styling

### 1. **Color Architecture**
- **Brand Colors**: 11-step scale from `#EEF6FF` to `#16245A`
- **Functional Colors**: Success (emerald), Warning (amber), Danger (rose), Info (blue)
- **Neutral Scale**: Comprehensive gray scale for text and backgrounds
- **Semantic Tokens**: Context-aware color usage (primary, secondary, muted, etc.)

### 2. **Typography System**
```css
/* Font scale from text-xxs (8px) to display-xl (60px) */
font-family: "Inter", "Poppins", sans-serif
text-base: 14px (default body)
line-height: Optimized for readability
```

### 3. **Spacing & Layout**
```css
/* 4px base unit system */
spacing/1: 4px   /* XS */
spacing/4: 16px  /* Component spacing */
spacing/6: 24px  /* Standard spacing */
spacing/8: 32px  /* Section padding */
spacing/16: 64px /* Large sections */
```

### 4. **Dark Mode Implementation**
```typescript
// Automatic theme switching
<ThemeProvider defaultTheme="system" storageKey="ui-theme">
  <div className="min-h-screen bg-background text-foreground">
    {/* App content */}
  </div>
</ThemeProvider>
```

## Responsive Design Patterns

### 1. **Mobile-First Approach**
```typescript
// Responsive grid layout
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  {/* Cards adapt to screen size */}
</div>

// Mobile sidebar transformation
const isMobile = useIsMobile(); // Custom hook for 768px breakpoint
// Sidebar becomes drawer/sheet on mobile
```

### 2. **Container Queries**
```css
/* Component-level responsiveness */
@container/card (min-width: 400px) {
  .card-content {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

## Accessibility Features

### 1. **Keyboard Navigation**
- Tab order management
- Arrow key navigation in menus
- Escape key handling for modals
- Enter/Space activation

### 2. **Screen Reader Support**
- ARIA labels and descriptions
- Live regions for dynamic content
- Role attributes for custom components
- Focus announcements

### 3. **Visual Accessibility**
- High contrast mode support
- Focus indicators
- Color-blind friendly palettes
- Reduced motion preferences

## State Management Patterns

### 1. **Form State**
```typescript
// React Hook Form with Zod validation
const form = useForm<FormData>({
  resolver: zodResolver(formSchema),
  defaultValues: {
    username: "",
    email: "",
  },
});
```

### 2. **Component State**
```typescript
// Sidebar state management
const { state, open, setOpen, isMobile } = useSidebar();

// Modal state
const [isOpen, setIsOpen] = useState(false);
```

### 3. **Theme State**
```typescript
// Theme context
const { theme, setTheme } = useTheme();
```

## Performance Optimization

### 1. **Code Splitting**
```typescript
// Lazy loading of components
const Dashboard = lazy(() => import('./Dashboard'));
const Analytics = lazy(() => import('./Analytics'));
```

### 2. **Memoization**
```typescript
// Prevent unnecessary re-renders
const MemoizedTable = memo(DataTable);
const memoizedValue = useMemo(() => computeExpensiveValue(data), [data]);
```

### 3. **Bundle Optimization**
- Tree shaking with ES modules
- Dynamic imports for large components
- Optimized bundle sizes with Radix UI

## Implementation Workflow

### 1. **Project Setup**
```bash
# Initialize new project with Next.js and TypeScript
npx create-next-app@latest my-backstage-app --typescript --tailwind --eslint

# Install core dependencies
npm install @radix-ui/react-* class-variance-authority clsx tailwind-merge
npm install react-hook-form @hookform/resolvers zod
npm install lucide-react
```

### 2. **Configuration Files**
```typescript
// tailwind.config.js - Theme configuration
// components.json - Shadcn/ui configuration
// tsconfig.json - TypeScript configuration
```

### 3. **Folder Structure**
```
src/
├── components/
│   ├── ui/           # Base UI components
│   ├── forms/        # Form components
│   ├── layout/       # Layout components
│   └── features/     # Feature-specific components
├── hooks/            # Custom hooks
├── lib/              # Utilities and configurations
├── styles/           # Global styles
└── types/            # TypeScript types
```

### 4. **Component Development Process**
1. Start with base Radix UI primitive
2. Apply Backstage design tokens
3. Add TypeScript types
4. Implement responsive behavior
5. Add accessibility features
6. Test with different themes
7. Document usage patterns

## Best Practices

### 1. **Component Design**
- Single responsibility principle
- Composable API design
- Consistent prop naming
- TypeScript-first development

### 2. **Styling Approach**
- Utility-first with Tailwind CSS
- Component variants with CVA
- CSS custom properties for themes
- Mobile-first responsive design

### 3. **Performance**
- Lazy load heavy components
- Optimize bundle sizes
- Use React's built-in optimization hooks
- Minimize prop drilling with context

### 4. **Accessibility**
- Test with screen readers
- Verify keyboard navigation
- Check color contrast ratios
- Validate HTML semantics

## Code Generation Templates

When generating applications with this skill, use the following patterns:

### 1. **Page Template**
```typescript
import { Button } from "@/components/ui/button";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

export default function PageName() {
  return (
    <div className="flex-1 space-y-4 p-4 md:p-8 pt-6">
      <div className="flex items-center justify-between">
        <h2 className="text-3xl font-bold tracking-tight">Page Title</h2>
        <Button>Action Button</Button>
      </div>
      <div className="grid gap-4 md:grid-cols-2 lg:grid-cols-4">
        {/* Content cards */}
      </div>
    </div>
  );
}
```

### 2. **Component Template**
```typescript
import * as React from "react";
import { cva, type VariantProps } from "class-variance-authority";
import { cn } from "@/lib/utils";

const componentVariants = cva(
  "base-styles",
  {
    variants: {
      variant: {
        default: "default-styles",
        secondary: "secondary-styles",
      },
      size: {
        default: "default-size",
        sm: "small-size",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
);

interface ComponentProps
  extends React.HTMLAttributes<HTMLDivElement>,
    VariantProps<typeof componentVariants> {
  // Additional props
}

const Component = React.forwardRef<HTMLDivElement, ComponentProps>(
  ({ className, variant, size, ...props }, ref) => {
    return (
      <div
        ref={ref}
        data-slot="component-name"
        className={cn(componentVariants({ variant, size, className }))}
        {...props}
      />
    );
  }
);

Component.displayName = "Component";

export { Component };
```

## Integration Guidelines

### 1. **API Integration**
- Use React Query for data fetching
- Implement loading states with Skeleton components
- Handle errors with Alert components
- Show success feedback with Toast notifications

### 2. **Authentication**
- Implement role-based access control
- Use context for auth state management
- Protect routes with auth guards
- Handle token refresh seamlessly

### 3. **Real-time Features**
- WebSocket integration patterns
- Live data updates with optimistic UI
- Notification systems
- Collaborative features

This skill generates modern, accessible, and maintainable web applications following enterprise standards while maintaining the distinctive Backstage design aesthetic. All generated code follows React best practices, TypeScript conventions, and accessibility guidelines.

## Usage Examples

When using this skill, specify:
1. **Application type** (dashboard, tool, CMS)
2. **Key features** needed
3. **Data structures** to work with
4. **User roles** and permissions
5. **Integration requirements**

The skill will generate complete, production-ready applications with:
- Responsive layouts
- Theme support
- Accessibility features
- Type safety
- Performance optimizations
- Best practice implementations