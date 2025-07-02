# TIL - 2025.07.02
# Vue에서 watch를 활용한 DOM 조작

## 개요
이미지 뷰어 라이브러리 사용 시, 이미지 확대 모드에서 툴바 배경 제거 및 버튼 숨김 처리를 위해 DOM을 직접 제어해야 했다.

## 핵심 코드

```js
watch(showViewer, (visible) => {
  if (visible) {
    setTimeout(() => {
      const toolbar = document.querySelector('.vel-toolbar')
      if (toolbar) {
        toolbar.style.backgroundColor = 'transparent'
        const toolbarBtns = document.querySelectorAll('.vel-toolbar .toolbar-btn')
        toolbarBtns.forEach(btn => btn.style.display = 'none')
      }
    }, 100)
  }
})