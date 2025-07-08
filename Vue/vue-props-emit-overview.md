# TIL - 2025.07.08

## 1. Props와 Emit

Vue에서 컴포넌트 간 데이터 전달은 단방향 흐름(one-way data flow)을 따른다.  
`props`는 부모 → 자식, `emit`은 자식 → 부모 방향으로 통신한다.

### 🔹 props

#### 개념
- 부모 컴포넌트가 자식 컴포넌트에 값을 전달할 때 사용
- 자식에서는 읽기 전용으로 사용해야 하며, 직접 수정하면 안 됨

#### 예시
```vue
<!-- 부모 -->
<ChildComponent :title="'안녕하세요'" />

<!-- 자식 -->
<script setup>
defineProps({
  title: String
})
</script>

<template>
  <h1>{{ title }}</h1>
</template>
```

### 🔹 emit

#### 개념
- 자식 컴포넌트가 부모에게 이벤트를 전달할 때 사용
- 이벤트 이름과 함께 데이터를 전달할 수 있음

#### 예시
```vue
<!-- 자식 -->
<script setup>
const emit = defineEmits(['send'])

function handleClick() {
  emit('send', 'Hello from child')
}
</script>

<template>
  <button @click="handleClick">Send</button>
</template>

<!-- 부모 -->
<ChildComponent @send="handleSend" />

<script setup>
function handleSend(msg) {
  console.log(msg) // Hello from child
}
</script>
```

### 정리

| 항목  | 방향         | 설명                    |
|-------|--------------|-------------------------|
| props | 부모 → 자식 | 데이터 전달             |
| emit  | 자식 → 부모 | 이벤트 및 값 전달       |

- `props`는 읽기 전용이며, 상태 변경이 필요할 경우 `emit`으로 부모에게 알리고 처리하는 구조를 사용
- `v-model`은 내부적으로 `props`와 `emit`을 조합하여 양방향 바인딩을 구성함