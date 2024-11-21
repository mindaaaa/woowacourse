
# ESLint와 Prettier 설정 및 커밋 제외 방법

## 목표
- **ESLint와 Prettier를 설치하지만 `package.json` 변경 내용은 커밋하지 않도록 설정**한다.
- **ESLint를 이용해 함수 길이 제한을 설정**하여 코드 스타일을 개선한다.
---
## 1. `Git`의 `update-index` 명령어 사용
- `package.json` 파일의 변경 사항을 Git이 추적하지 않도록 설정: 
```
bash git update-index --skip-worktree package.json
```
 - 필요 시 다시 추적하도록 설정하려면:
```
 git update-index --no-skip-worktree package.json
```

## 2. `ESLint`로 함수 길이 제한 설정
### ESLint 설치
- 프로젝트에 ESLint를 설치:
```
npm install eslint --save-dev
```

### `max-lines-per-function` 규칙 설정
- `.eslintrc` 또는 `.eslintrc.json` 파일에 다음 규칙 추가:
```json
{
  "rules": {
    "max-lines-per-function": [
      "error", 
      {
        "max": 12, // 함수당 최대 라인 수
        "skipBlankLines": true, // 빈 줄 제외
        "skipComments": true // 주석 제외
      }
    ]
  }
}
```
- 자세한 내용은 [max-lines-per-function 규칙](https://eslint.org/docs/latest/rules/max-lines-per-function) 문서를 참조.
---
## 참고
- Git에서 `package.json` 변경을 제외하는 방법을 활용하면 ESLint 설치가 프로젝트 코드와 충돌하지 않도록 관리가 가능하다.