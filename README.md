# 프로젝트 개요

본 문서는 본 프로젝트의 개발 환경, 협업 전략, 브랜치 규칙 및 컨벤션을 정의한 가이드라인입니다. 본 프로젝트는 대학 학기작 프로젝트로 진행됩니다.

---

## 1. 개발 환경 및 언어

- **Unity 버전**: 6000.6.0f1
- **개발 언어**: 
  - C# (Unity 지원 닷넷 버전)
  - HLSL (사용 가능한 개발자 한정 적용)

---

## 2. 협업 전략 및 브랜치 관리

본 프로젝트는 소규모 개발 인원의 특성에 맞추어 유연하게 변형된 [GIT-FLOW 협업 전략](https://www.youtube.com/watch?v=EV3FZ3cWBp8&source_ve_path=OTY3MTQ&embeds_referring_euri=https%3A%2F%2Fvelog.io%2F)을 채택하여 관리합니다.

### 브랜치 규칙 및 사용자별 권한

첨부된 규칙 설정에 따라 각 브랜치별로 사용자 접근 권한과 룰이 엄격히 적용됩니다.

1. **메인 브랜치 규칙**
   - 첨부된 규칙 설정(`메인 브랜치 PR 규칙`)에 의거하여, `main` 브랜치는 직접적인 푸시가 불가능합니다.
   - 모든 변경 사항은 반드시 Pull Request를 거쳐야 하며, 강제 푸시(Force Push) 및 삭제가 차단됩니다.
   - ![메인 브랜치 PR 규칙](image_c3fa83.png)

2. **직군별 브랜치 접근 제한 규칙**
   - 첨부된 규칙 설정(`타 직군 브랜치 접근 제한`)에 의거하여, 지정된 예외 권한을 가진 사용자 외에는 업데이트가 제한됩니다.
   - ![타 직군 브랜치 접근 제한](image_c3fb00.png)

3. **아트 리소스 취합자 전용 규칙**
   - (이펙트 리소스 취합자)는 오직 `resources/assets` 브랜치에만 접근 및 작업이 허용됩니다.

---

## 3. 코딩 및 커밋 컨벤션

### C# 명명 규칙
프로젝트 내 모든 C# 스크립트 작성 시 아래의 공식 명명 규칙을 준수해야 합니다.
- [C# 명명 규칙](https://learn.microsoft.com/ko-kr/dotnet/csharp/fundamentals/coding-style/identifier-names)

### 커밋 메시지 컨벤션
모든 커밋 메시지는 아래의 표준 규칙을 따르어야 합니다.
- [커밋 메시지 규칙](https://www.conventionalcommits.org/en/v1.0.0/)

#### 커밋 메시지 형식 리스트
- `feat`: 새로운 기능 추가
- `fix`: 버그 수정
- `docs`: 문서 수정
- `style`: 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
- `refactor`: 코드 리팩토링
- `test`: 테스트 코드 추가 및 수정
- `chore`: 빌드 업무 수정, 패키지 매니저 수정 등 기타 작업

---

## 4. 폴더 명명 규칙 (Directory Naming Convention)

사용자 지정 폴더 명명 규칙은 추후 팀 회의를 통해 최종 확정될 예정이며, 현재 도식화된 양식은 다음과 같습니다. 커밋 메시지 컨벤션의 구조를 차용하여 직관적으로 구성합니다.

```text
Root/
├── Assets/
│   ├── _Scripts/        # 소스 코드 (C#, HLSL)
│   ├── _Prefabs/        # 프리팹 에셋
│   ├── _Scenes/         # 씬 파일
│   ├── _Materials/      # 머티리얼 및 셰이더
│   ├── _Textures/       # 텍스처 리소스
│   ├── _Animations/     # 애니메이션 클립 및 컨트롤러
│   └── _Audio/          # 오디오 리소스
└── Settings/            # 프로젝트 설정 파일
```

---

## 5. Git LFS (Large File Storage) 설정 및 트랙 항목

대용량 리소스 파일의 효율적인 관리를 위해 `.gitattributes` 파일에 정의된 Git LFS 트랙 항목입니다. 해당 확장자를 가진 파일들은 LFS를 통해 관리됩니다.

## Git LFS 트랙 대상 확장자 목록

### 3D Models
- `*.fbx`
- `*.obj`
- `*.blend`
- `*.max`

### Textures & Images
- `*.png`
- `*.jpg`
- `*.jpeg`
- `*.psd`
- `*.tga`
- `*.exr`
- `*.tif`
- `*.tiff`
- `*.bmp`

### Audio
- `*.wav`
- `*.mp3`
- `*.ogg`
- `*.aif`

### Video
- `*.mp4`
- `*.mov`
- `*.webm`

### Fonts
- `*.ttf`
- `*.otf`

### Archives & Binaries
- `*.zip`
- `*.rar`
- `*.7z`
- `*.dll`
- `*.so`
- `*.a`
