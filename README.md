# 카페 키오스크

`dist` 디렉터리에 배포 가능한 정적 사이트가 들어 있습니다. 별도의 Python 패키지 설치나 빌드 과정은 필요하지 않습니다.

## Render 배포

1. 이 커밋을 GitHub에 푸시합니다.
2. Render에서 **New > Blueprint**를 선택하고 저장소를 연결합니다. 루트의 `render.yaml`이 정적 사이트 설정을 제공합니다.
3. Blueprint를 적용해 배포합니다.

직접 설정하려면 **New > Static Site**에서 저장소와 브랜치를 연결하고 다음 값을 입력합니다.

- Build Command: `test -f dist/index.html`
- Publish Directory: `dist`

기존에 만든 Python Web Service는 Static Site로 유형을 변경할 수 없으므로, 새 Static Site 또는 Blueprint를 만들어야 합니다. 기존 서비스는 새 배포를 확인한 뒤 필요에 따라 정리하세요.
