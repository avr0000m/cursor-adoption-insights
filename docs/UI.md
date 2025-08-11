# UI Primitives (shadcn/radix wrappers)

All components live under `src/components/ui`. They primarily forward props to their underlying elements/Radix primitives with Tailwind styles. Common exports:

- Layout and surfaces: `Card`, `CardHeader`, `CardContent`, `CardFooter`, `CardTitle`, `CardDescription`, `Separator`, `ScrollArea`, `ResizablePanelGroup`...
- Inputs: `Input`, `Textarea`, `RadioGroup`, `RadioGroupItem`, `Checkbox`, `Switch`, `Slider`, `Select` family, `InputOTP` family.
- Feedback: `Alert` family, `Toast`/`Toaster`, `Skeleton`, `Progress`.
- Navigation/menus: `Tabs` family, `DropdownMenu` family, `ContextMenu` family, `NavigationMenu` family, `Menubar` family, `Breadcrumb`.
- Overlay: `Dialog`, `AlertDialog`, `Drawer`, `Popover`, `HoverCard`, `Sheet`, `Tooltip` family.
- Data display: `Table` family, `Badge`, `Avatar`, `Carousel`, `Chart` helpers.
- Misc: `Accordion`, `AspectRatio`, `Toggle`, `ToggleGroup`, `Sonner` toaster wrapper.

## Imports

```tsx
import { Button } from '@/components/ui/button'
import { Card, CardHeader, CardContent, CardTitle } from '@/components/ui/card'
import { Tabs, TabsList, TabsTrigger, TabsContent } from '@/components/ui/tabs'
import { useToast, toast } from '@/components/ui/use-toast'
```

## Examples

### Button
```tsx
<Button variant="outline">Click me</Button>
```

### Card
```tsx
<Card>
  <CardHeader>
    <CardTitle>Title</CardTitle>
  </CardHeader>
  <CardContent>Content</CardContent>
</Card>
```

### Tabs
```tsx
<Tabs defaultValue="account">
  <TabsList>
    <TabsTrigger value="account">Account</TabsTrigger>
    <TabsTrigger value="password">Password</TabsTrigger>
  </TabsList>
  <TabsContent value="account">Account form</TabsContent>
  <TabsContent value="password">Password form</TabsContent>
</Tabs>
```

### Toasts
```tsx
// Render once near root
<Toaster />

// In a component
const { toast } = useToast()
toast({ title: 'Saved', description: 'Your changes were saved.' })
```

For advanced props, refer to each component source under `src/components/ui`.