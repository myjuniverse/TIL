# TIL - 2025.07.08
# Vue.js 입문 시 필수 개념 정리 (Vue 3 기준)

## ✅ 1. Vue의 핵심 개념 구조
- MVVM(Model-View-ViewModel) 패턴 기반
- template + script + style → 컴포넌트 단위 구성
- 반응형(Reactivity) 시스템이 핵심: `ref`, `reactive`

---

## ✅ 2. 기초 개념

### 2-1. 컴포넌트(Component)
- 재사용 가능한 UI 단위
- `<MyComponent />` 형태로 사용, `props`로 데이터 전달

### 2-2. 템플릿 문법 (Template Syntax)
- `{{ message }}`: Mustache 문법
- 주요 디렉티브: `v-bind`, `v-model`, `v-if`, `v-for`, `v-on`

### 2-3. 반응형 상태 관리
- `ref()`: 기본형 데이터 (string, number 등)
- `reactive()`: 객체, 배열 등 복합형 데이터
- `watch`, `computed`도 핵심 도구

---

## ✅ 3. 핵심 디렉티브 사용법

| 디렉티브    | 용도              |
|-------------|-------------------|
| `v-model`   | 양방향 바인딩     |
| `v-bind` (`:`) | 속성 바인딩    |
| `v-on` (`@`)   | 이벤트 등록     |
| `v-if`, `v-show` | 조건부 렌더링 |
| `v-for`     | 반복 렌더링       |

---

## ✅ 4. Composition API vs Options API
- Vue 3에서는 Composition API가 공식 권장 방식
```vue
<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>
```

---

## 💻 mac 백틱(`) 
영문으로 ₩ 입력시 ` 사용가능