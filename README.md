# jy-data-ui-kit

Professional data visualization and management React components built with styled-components.

## Features

- 8 specialized data components
- DataTable with sorting, filtering, pagination
- Interactive charts powered by Recharts
- TreeView for hierarchical data
- Full dark mode support via `$isDark` prop
- TypeScript support with full type definitions

## Installation

```bash
npm install jy-data-ui-kit
```

### Peer Dependencies

```bash
npm install react react-dom styled-components lucide-react recharts
```

## Usage

```tsx
import { DataTable, DataChart, TreeView } from 'jy-data-ui-kit';

const columns = [
  { key: 'name', label: 'Name', sortable: true },
  { key: 'email', label: 'Email' },
  { key: 'role', label: 'Role', filterable: true },
];

function App() {
  return (
    <DataTable
      columns={columns}
      data={users}
      $isDark={false}
      pageSize={10}
    />
  );
}
```

## Components

| Component | Description |
|---|---|
| `DataTable` | Full-featured table with sorting, filtering, pagination |
| `DataChart` | Interactive charts (bar, line, area, pie) via Recharts |
| `DataList` | Styled data list with actions |
| `TreeView` | Expandable/collapsible tree for hierarchical data |
| `SearchFilter` | Combined search input with filter controls |
| `MultiSelect` | Multi-value select with tags |
| `DateTimePicker` | Date and time picker component |
| `Chart` | Lightweight chart wrapper |

## License

MIT
