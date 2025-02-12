
브라우저 렌더링 과정에서 다음과 같은 경우에 리렌더링이 발생하게 됩니다.
1. 자바스크립트에 의해 노드 추가 또는 삭제
2. 브라우저 창의 리사이징에 의한 뷰포트 크기 변경
3. HTML 요소의 레이아웃에 변경을 발생시키는 스타일 변경
위의 경우에는 Layout 계산과 Paint 과정이 재차 실행되어 리렌더링이 발생하게 됩니다.

이 과정에서 **Layout 계산을 다시 수행하는 것을 Reflow**, **픽셀을 렌더링하는 Paint 작업을 다시 하는 것을 Repaint**라고 합니다. 

Reflow가 발생하면 Repaint가 무조건 발생하므로 성능에 큰 영향을 미칠 수 있습니다. 되도록 Reflow를 발생시키지 않도록 주의해야합니다.
## Reflow
* DOM 엘리먼트 추가, 제거 또는 변경
* CSS 스타일 추가, 제거 또는 변경
* CSS 스타일을 직접 변경하거나, 클래스를 추가함으로써 레이아웃이 변경될 수 있습니다. 엘리먼트의 크기나 위치를 변경하면, DOM 트리에 있는 다른 노드에 영향을 줄 수 있습니다. 
* CSS3 애니메이션과 트랜지션. 애니메이션의 모든 프레임에서 리플로우가 발생합니다.

* DOM 요소의 위치와 크기를 다시 계산하는 Layout 과정입니다. 
* 렌더 트리를 다시 생성하므로 성능에 큰 영향을 미칠 수 있고, 상위 엘리먼트가 변경되면 하위 엘리먼트에도 영향을 미칩니다. 

## Repaint
* 가시성이 변경되는 순간 (opacity, background-color, visibility, outline)
- Reflow가 실행된 순간 뒤에 실행됩니다. 

- Layout 과정에는 영향을 미치지 않고 변경된 요소를 화면에 그려줄 때 발생합니다.

## 🛠️ 용어 공부

### ⚙️ Reflow
- 생성된 DOM 노드의 레이아웃 수치(너비, 높이, 위치 등) 변경 시 영향 받은 모든 노드의(자신, 자식, 부모, 조상(결국 모든 노드) ) 수치를 다시 계산하여(Recalculate), 렌더 트리를 재생성하는 과정을 Reflow 라고 합니다.

### ⚙️ Repaint
- Reflow 과정이 끝난 후 재 생성된 렌더 트리를 다시 그리게 되는데 이 과정을 Repaint 라고 합니다.