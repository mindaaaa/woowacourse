## CommonJS

- **Node.js** 환경에서 주로 사용하는 **모듈 시스템**.
- `require()` 함수를 사용해 모듈을 가져오고, `module.exports`를 사용해 모듈을 내보냄.

### 장점
- **동기적 로드 방식**을 이용.
- 서버 사이드 렌더링 환경에서 유리.
- 모든 모듈이 로드된 후 코드가 실행되므로 안정적.

### 단점
- **트리 셰이킹**(사용하지 않는 코드 제거)이 어려움.
- 동적 로드를 지원하지만, 사용되지 않는 코드 제거가 힘듦.
- **브라우저 환경**에서 사용이 어려움(번들링 필요).

---

## ES Module

- `import`와 `export` 키워드를 사용해 모듈을 가져오고 내보냄.
- 비동기적으로 작동하여 **브라우저 환경**에서 사용 가능.
- 코드의 **가독성을 높이고** 모듈 간 의존성을 명확히 함.

### 코드 예시
```javascript
// 모듈 가져오기
import { LottoIssuer } from './LottoIssuer.js';

LottoIssuer();

// 모듈 내보내기
export function setLotto() {
  // 생략
}
```

### 장점
- 비동기 로드 방식으로 **브라우저 친화적.**
- **트리 셰이킹** 지원: 사용되지 않는 코드를 제거하기 쉬움.
- 최신 JavaScript 표준으로 코드 가독성과 관리가 쉬움.

### 단점
- 일부 레거시 환경에서는 지원하지 않음(트랜스파일링 필요).

---

## 요약

| 특징     | CommonJS             | ES Module          |
| ------ | -------------------- | ------------------ |
| 로드 방식  | 동기적                  | 비동기적               |
| 트리 셰이킹 | 어려움                  | 용이                 |
| 사용 환경  | 서버 사이드               | 브라우저               |
| 키워드    | `require`, `exports` | `import`, `export` |
## 선택 기준
- **Node.js** 환경에서 실행되는 서버 코드라면 **CommonJS** 사용.
- 브라우저 및 최신 **JavaScript 환경**에서는 **ES Module**을 권장.