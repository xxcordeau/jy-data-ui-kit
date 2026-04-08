# 📊 jy-data-ui-kit 
( React / TypeScript / Recharts ) | Professional Data Visualization React Components

데이터 시각화 및 데이터 관리에 특화된 React 컴포넌트 라이브러리입니다.  
테이블, 차트, 트리뷰, 필터 등 데이터 중심 UI에 필요한 컴포넌트를 제공합니다.

[![npm version](https://img.shields.io/npm/v/jy-data-ui-kit)](https://www.npmjs.com/package/jy-data-ui-kit)
[![license](https://img.shields.io/npm/l/jy-data-ui-kit)](./LICENSE)

---

## 특징

- 데이터 중심 UI — 테이블 정렬/검색, 트리 구조, 멀티셀렉트 등 실무 중심 컴포넌트
- 다크모드 — 모든 컴포넌트에 `isDark` prop으로 개별 제어
- Recharts 기반 차트 — Line, Bar, Area, Pie 차트 지원
- TypeScript — 완전한 타입 지원
- Tree-shakable — 사용한 컴포넌트만 번들에 포함
- `styled-components` 기반 — 별도 CSS 설정 불필요

---

## 설치

```bash
npm install jy-data-ui-kit
```

### 피어 의존성 설치

```bash
npm install react react-dom styled-components lucide-react recharts
```

---

## 사용법

```tsx
import { DataTable, DataChart, SearchFilter } from 'jy-data-ui-kit';

const columns = [
  { key: 'name', label: '이름', sortable: true },
  { key: 'status', label: '상태' },
  { key: 'date', label: '날짜', sortable: true },
];

const data = [
  { name: '홍길동', status: '활성', date: '2025-01-01' },
  { name: '김철수', status: '비활성', date: '2025-01-02' },
];

export default function App() {
  return (
    <DataTable
      title="사용자 목록"
      columns={columns}
      data={data}
      isDark={false}
      searchable
      filterable
    />
  );
}
```

---

## 컴포넌트 목록

### DataTable

정렬, 검색, 필터를 내장한 데이터 테이블입니다.

```tsx
import { DataTable } from 'jy-data-ui-kit';

<DataTable
  title="주문 목록"
  columns={columns}   // { key, label, sortable?, render? }[]
  data={data}
  isDark={false}
  searchable          // 검색 입력창 표시
  filterable          // 필터 버튼 표시
/>
```

### DataChart

Line, Bar, Area, Pie 차트를 하나의 컴포넌트로 지원합니다.

```tsx
import { DataChart } from 'jy-data-ui-kit';

<DataChart
  title="월별 매출"
  type="bar"          // 'line' | 'bar' | 'area' | 'pie'
  data={chartData}    // Recharts 표준 데이터 형식
  dataKeys={['매출', '비용']}
  isDark={false}
/>
```

### DataList

리스트 형태의 데이터 표시 컴포넌트입니다.

```tsx
import { DataList } from 'jy-data-ui-kit';

<DataList
  title="최근 활동"
  items={items}       // { id, title, subtitle?, badge?, icon? }[]
  isDark={false}
/>
```

### TreeView

파일 시스템 구조처럼 계층적 데이터를 표시합니다.  
노드 선택, 펼치기/접기를 지원합니다.

```tsx
import { TreeView } from 'jy-data-ui-kit';

const treeData = {
  id: 'root',
  label: '프로젝트',
  children: [
    { id: 'src', label: 'src', children: [
      { id: 'app', label: 'App.tsx' }
    ]},
  ]
};

<TreeView
  title="파일 구조"
  data={treeData}
  onSelect={(node) => console.log(node)}
  isDark={false}
/>
```

### SearchFilter

검색어 입력과 필터 태그를 조합한 필터 바 컴포넌트입니다.

```tsx
import { SearchFilter } from 'jy-data-ui-kit';

<SearchFilter
  placeholder="검색..."
  filters={[
    { key: 'status', label: '상태', options: ['전체', '활성', '비활성'] },
    { key: 'type', label: '유형', options: ['전체', 'A', 'B'] },
  ]}
  onSearch={(value) => console.log(value)}
  onFilterChange={(filters) => console.log(filters)}
  isDark={false}
/>
```

### MultiSelect

체크박스 기반 다중 선택 드롭다운입니다.

```tsx
import { MultiSelect } from 'jy-data-ui-kit';

<MultiSelect
  options={['React', 'TypeScript', 'Node.js', 'Python']}
  selected={selected}
  onChange={setSelected}
  placeholder="기술 스택 선택"
  isDark={false}
/>
```

### DateTimePicker

날짜와 시간을 함께 선택하는 피커 컴포넌트입니다.

```tsx
import { DateTimePicker } from 'jy-data-ui-kit';

<DateTimePicker
  value={date}
  onChange={setDate}
  isDark={false}
/>
```

### Chart

Recharts의 저수준 차트 구성 요소를 래핑한 컴포넌트입니다.  
커스텀 차트가 필요할 때 사용합니다.

---

## 다크모드

모든 컴포넌트는 `isDark` prop으로 독립적으로 다크모드를 적용합니다.

```tsx
const isDark = window.matchMedia('(prefers-color-scheme: dark)').matches;

<DataTable isDark={isDark} ... />
```

---

## 빌드

```bash
# 빌드
npm run build

# 개발 (watch 모드)
npm run dev
```

빌드 결과물은 `dist/` 에 생성됩니다.

---

## 함께 사용하면 좋은 패키지

[jy-awesome-ui](https://www.npmjs.com/package/jy-awesome-ui) — 버튼, 카드, 뱃지 등 범용 UI 컴포넌트 라이브러리

---

## 라이선스

MIT
