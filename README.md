# 초록섬 — GitHub / Netlify 간편 업로드 버전

동물 주민과 대화하고, 사과를 모으고, 나무와 집을 배치하는 3D 마을입니다.

**이번 버전은 파일이 모두 같은 위치에 있습니다. 폴더를 따로 만들 필요가 없습니다.**

## GitHub에 올리는 방법

1. ZIP 파일의 압축을 풉니다.
2. 압축을 푼 위치에서 `index.html`, `main.js`, `package.json`, `netlify.toml`이 함께 보이는지 확인합니다.
3. GitHub의 `animal` 저장소를 엽니다.
4. `Add file → Upload files`를 누릅니다.
5. 이 폴더 **안에 있는 파일을 전부** 끌어다 놓습니다. ZIP 파일이나 바깥 폴더는 올리지 않습니다.
6. `Commit changes`를 누릅니다. 같은 이름의 기존 파일은 새 버전으로 교체됩니다.

파일이 저장소 첫 화면에 나란히 보이면 맞습니다. `src` 폴더가 필요하지 않습니다. 앞서 올린 `deploy.yml`, 설명 문서, 이미지가 남아 있어도 Netlify 게임 빌드에는 영향이 없습니다.

## Netlify에서 실행

GitHub의 이 저장소가 연결된 Netlify 프로젝트를 엽니다. 새 배포가 자동으로 시작되지 않으면 `Deploys`에서 새 배포를 실행합니다.

포함된 `netlify.toml`이 다음 값을 지정합니다.

| 설정 | 값 |
| --- | --- |
| Build command | `npm run build` |
| Publish directory | `dist` |
| Node.js | `24` |

저장소 첫 화면에 `package.json`이 있으므로 별도의 하위 폴더를 Base directory로 지정하지 마세요. 정상 배포가 끝난 뒤 Netlify의 사이트 주소를 열면 됩니다.

## 내 컴퓨터에서 실행

Node.js 22.12 이상이 필요합니다.

```sh
npm ci
npm run dev
```

검사와 빌드는 다음 명령으로 실행합니다.

```sh
npm test
npm run build
```

`index.html`을 더블클릭하는 방식으로는 실행하지 마세요. `npm run dev`에서 표시되는 주소로 접속하거나 Netlify에 공개된 주소를 사용합니다.

## 조작

- WASD / 방향키: 이동
- E: 가까운 주민과 대화하거나 사과 줍기
- Enter: 대화 이어 가기
- 마을 꾸미기: 나무 또는 집 선택 후 빈 잔디 클릭
- 마지막 배치 취소: 가장 최근에 놓은 물건 되돌리기
- ＋ / − / 마우스 휠: 확대·축소
- ?: 도움말과 초기화
- 모바일: 화면 아래 방향 버튼으로 이동

수집한 사과와 배치한 물건은 현재 브라우저에 저장됩니다. 주민 인사 목표는 새로고침하면 초기화됩니다. 혼자 즐기는 버전으로, 실시간 다중 접속은 포함하지 않습니다.

## 파일 안내

- `index.html`: 게임 화면
- `main.js`: 이동, 대화, 꾸미기, 저장 연결
- `world.js`: 섬·집·주민 3D 도형
- `state.js`: 주민 대사, 수집·배치·충돌 처리
- `input.js`: 한글 키보드 조작 지원
- `style.css`: 화면 디자인
- `input.test.js`, `state.test.js`: 기능 검사
- `package.json`, `package-lock.json`: 실행과 빌드에 필요한 설정
- `netlify.toml`: Netlify 공개 설정

동물의 숲에서 영감을 받은 독립 프로젝트이며 닌텐도와 관계가 없습니다. 원작 이미지·캐릭터·음악을 사용하지 않습니다. 직접 작성한 코드와 도형은 MIT 라이선스이며 외부 라이브러리와 글꼴은 각각의 라이선스를 따릅니다.
