# farmion
스터디 프로젝트: 스프링부트 기반 세션 모집 웹사이트
<br>
## 🙏🏻 Git 협업 전략
**Commit Convention**

| Commit Type | Description |
| --- | --- |
| Feat | 기능 개발 |
| Fix | 버그 수정 |
| Docs | 문서 수정 |
| Refactor | 코드 리팩토링 |
| Design | CSS 등 사용자 UI 변경 |
| Test | 로직 및 코드 테스트 |

**PR Convention**

| Icon | 사용법 | Description |
| --- | --- | --- |
| 🎨 Design | `:art` | UI/스타일 파일 추가/수정 |
| ✨ Feature | `:sparkles` | 새로운 기능 도입 |
| 🔥 Fix | `:fire` | 버그 수정 |
| ✅ Test | `:white_check_mark`   | 로직 및 코드 테스트 |
| ♻️ Refactoring | `:recycle` | 코드 리팩토링 |
| 📘 Docs | `:blue_book` | Feature 이외에 문서 생성 및 수정 |

## 📌 Git/GitHub Workflow

### **📋 역할 분담**

  * **리더:** GitHub Organization에 **Repository**를 생성하고, `main` 브랜치와 `dev` 브랜치를 초기 설정합니다.
  * **팀원:** Repository를 `clone`하여 개인 로컬 환경에서 개발을 시작합니다.
      * 기능 개발 시 **feature 브랜치**를 생성하여 작업합니다.
      * 작업 완료 후에는 `dev` 브랜치로 \*\*Pull Request(PR)\*\*를 보냅니다.
      * PR은 본인이 직접 확인 후 **merge**합니다.
      * merge가 끝나면 `dev` 브랜치의 최신 코드를 **동기화**합니다.

-----

### **🛠️ 개발 시작**

#### **1. Issue 생성**

새로운 기능이나 작업을 시작하기 전에 GitHub에서 **Issue**를 생성해주세요.

#### **2. Branch 생성**

`dev` 브랜치에서 새로운 브랜치를 생성하고 작업합니다.

  * **브랜치 네이밍 규칙:**
      * **새로운 기능:** `feature/#[이슈번호]`
      * **버그 픽스:** `fix/#[이슈번호]`
      * **리팩토링:** `refactor/#[이슈번호]`

#### **3. Branch 가져오기**

로컬에서 다음 명령어를 통해 최신 코드를 가져오고, 브랜치를 생성하여 이동합니다.

```
git fetch origin
git switch -c feature/#3-post-crud origin/dev
```

이제 해당 브랜치에서 기능 개발을 진행합니다.

-----

### **✅ 개발 종료**

#### **1. Commit & Push**

작업이 끝나면 변경사항을 커밋하고 푸시합니다.

```
git add .
git commit -m "feat: 게시글 작성 기능 추가"
git push origin feature/#3-post-crud
```

#### **2. Pull Request (PR) 생성**

GitHub에서 `dev` 브랜치를 대상으로 PR을 생성합니다.

  * **base:** `dev`
  * **compare:** `feature/...`

#### **3. Squash and Merge**

**본인이 직접** PR을 확인하고 **Squash and Merge**를 진행합니다.

> 리뷰 과정은 생략하고, 자신의 파트에 대한 책임 하에 직접 머지합니다.

#### **4. 최신 코드 동기화**

Merge가 완료되면, 로컬에서 `dev` 브랜치로 돌아와 최신 코드를 동기화합니다.

```
git switch dev
git pull origin dev
```

-----

### **🚀 Main 브랜치 갱신**

  * 특정 마일스톤(예: 중간 시연, 최종 발표)에 도달하면 `dev` → `main` 브랜치로 **PR**을 엽니다.
  * **리더**가 PR을 머지하여 `main` 브랜치 상태를 갱신합니다.
  * `main` 브랜치는 항상 **"동작이 보장된"** 상태를 유지해야 합니다.
