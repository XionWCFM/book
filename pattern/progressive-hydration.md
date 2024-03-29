# progressive hydration이란?

페이지에서 덜 중요한 부분이 있을 수 있습니다.

그러한 부분의 경우에는 자바스크립트 번들을 지연로딩하는 것을 통해 한정된 자원에서 최선의 성능을 뽑아내고자 하는 발상에서 나온 기술이라고 볼 수 있습니다.

서버에서 HTML, CSS, JSON 데이터를 포함한 HTML 콘텐츠를 만들고 즉시 클라이언트에 전송하면

서버에서 마크업을 미리 만들어서 주었기 때문에 클라이언트는 빠르게 화면을 출력할 수 있습니다.

즉 꽤 빠른 FCP (First Contentful Paint)를 이룰 수 있죠

하지만 FCP가 빨랐다고해서 항상 TTI(Time to Interaction)이 빠른것은 아닙니다.

사용자가 유의미한 상호작용을 하려면 자바스크립트 번들이 로드되어야하기 때문이죠

<br/>

서버로부터 받은 DOM 요소들이 완전히 하이드레이션 되기 까지는 시간이 걸릴 수 밖에 없습니다.

컴포넌트가 hydrate 가능해지기 전 까지 자바스크립트 파일들은 로드되고 처리되며 실행됩니다.

이때 모든 앱을 한번에 hydrate 하는 대신 점진적으로 우선순위가 높은 순서부터 hydrate 하면 어떨까요?

<br/>

앱을 점진적으로 하이드레이션 하는 것을 통해 페이지 내에서 덜 중요한 부분을 지연시키면

자바스크립트의 번들 크기를 줄일 수 있고 사용자가 필요로하는 노드만 하이드레이션할 수 있습니다.

이러한 점진적인 하이드레이션은 서버사이드렌더링의 리하이드레이션 과정에서

서버가 렌더링한 돔트리가 제거되고 다시 만들어질 때 발생할 수 있는 문제를 겪지 않게도 해줄 수있어요

