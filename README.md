# 카페 키오스크

`dist` 디렉터리에 배포 가능한 정적 사이트가 들어 있습니다. 별도의 Python 패키지 설치나 빌드 과정은 필요하지 않습니다.

## Render 배포

1. 이 커밋을 GitHub에 푸시합니다.
2. Render에서 **New > Blueprint**를 선택하고 저장소를 연결합니다. 루트의 `render.yaml`이 정적 사이트 설정을 제공합니다.
3. Blueprint를 적용해 배포합니다.

직접 설정하려면 **New > Static Site**에서 저장소와 브랜치를 연결하고 다음 값을 입력합니다.

- Build Command: `test -f dist/index.html`
- Publish Directory: `dist`

### 기존 Python Web Service 사용하기

기존 서비스에서 배포하려면 Render의 **Settings > Build & Deploy**에서 브랜치가 `main`이고 Root Directory가 비어 있는지 확인한 뒤 다음 명령을 설정합니다.

- Build Command: `pip install -r requirements.txt`
- Start Command: `python -m http.server $PORT --bind 0.0.0.0 --directory dist`

`requirements.txt`는 의존성이 없으므로 비어 있습니다. 설정을 저장하고 최신 커밋을 수동으로 다시 배포하세요. `render.yaml`은 Blueprint로 새 정적 사이트를 만들 때 사용되며, 기존 Web Service의 설정을 자동으로 바꾸지 않습니다.
