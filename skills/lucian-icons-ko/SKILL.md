---
name: lucian-icons-ko
description: Lucian Icons의 움직이는 SVG 아이콘을 이름이나 갤러리 번호로 찾아 기존 웹 프로젝트에 적용할 때 사용한다. 실제 동작 상태에 맞는 애니메이션 연결도 지원한다. 전체 화면 재설계나 백엔드 구현용은 아니다.
---

# Lucian Icons 한국어 사용 안내

Lucian Icons 2.0.13은 오프라인으로 쓸 수 있는 애니메이션 아이콘 211개를 제공한다. 카탈로그 번호는 이 버전에 한정된다. 이 파일이 있는 폴더를 `<skill-dir>`로 쓴다. CLI는 Node.js 18 이상이 필요하며 별도 패키지 설치가 필요 없다. [갤러리](https://lucianlabs.dev/icons/)에서 아이콘을 확인할 수 있다.

1. 대상 프로젝트의 프레임워크, 테마, 아이콘 위치, 기존 버튼의 이름과 이벤트, 실제 상태 소스를 확인한다.
2. 한국어 또는 영어로 찾는다. 번호가 있으면 번호를 쓴다. 추천 요청이면 각 기능에 맞는 아이콘과 선택 이유를 알려준다.

   ```sh
   node <skill-dir>/scripts/lucian-icons.mjs search 다운로드
   node <skill-dir>/scripts/lucian-icons.mjs search 197
   ```

3. 필요한 아이콘만 확인하고 대상 프로젝트의 별도 폴더에 복사한다. 이 명령은 런타임과 아이콘의 무결성을 확인한다. 기존 파일이 같으면 유지하고 다르면 덮어쓰지 않는다. 다른 버전과 충돌하면 런타임의 `VERSION`을 비교하고 새 폴더를 사용한다.

   ```sh
   node <skill-dir>/scripts/lucian-icons.mjs get download
   node <skill-dir>/scripts/lucian-icons.mjs get download --out ./src/vendor/lucian-icons
   ```

4. [적용 안내](references/porting.md)를 읽고 선택한 모듈과 같은 폴더의 `runtime.js`를 사용한다. 원본 그림과 동작을 보존한다. 선은 `currentColor`를 따른다. 어두운 테마에는 `color-scheme: dark`를 유지하거나 추가한다. 단색은 `tone="line"`, 강조색은 `accent` 또는 `--li-accent`를 사용한다. 장식용 아이콘에는 기존 버튼 이름을 유지하고, 아이콘 자체가 의미를 전달하면 한국어 `label`을 지정한다. 기존 제어 요소 안에 넣고 버튼을 중첩하지 않는다.
5. 실제 상태와 아이콘 상태를 연결한다. 클릭을 성공으로 간주하지 않는다. 비동기 작업이 해결되면 성공, 실패하면 오류, 취소하면 취소에 맞는 상태를 적용한다. 진행률은 실제 측정값이 있을 때만 전달한다. 상태가 없는 아이콘에 임의 상태를 만들지 않는다. 갤러리의 타이머나 데모 핸들러를 제품 동작에 사용하지 않는다.
6. 키보드, 터치, 두 테마, 동작 줄이기 설정, 빠른 상반 입력, 중복 아이콘, 제거 후 재삽입과 실제 실패 경로를 확인한다. 완료한 검사와 못 한 검사를 구분해 보고한다. MIT 저작권 및 라이선스를 유지한다.

1.x에서 이전하는 경우 [마이그레이션 안내](references/migration.md)를 읽는다. [다운로드 예제](examples/download.html)는 사용자가 직접 성공·실패·취소를 선택하는 시험용 예제다. 웹 앱의 실제 작업 로직을 대신하지 않는다.
