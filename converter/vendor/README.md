# Vendor Libraries

이 디렉터리에는 오프라인에서도 동작하는 로컬 전용 파일 변환 도구를 위한 라이브러리들이 포함되어 있습니다.

## 포함된 라이브러리들

### PDF.js (pdfjs-dist)
- **경로**: `pdfjs-dist/build/`
- **파일들**:
  - `pdf.min.mjs` - PDF 파싱 및 렌더링 라이브러리 
  - `pdf.worker.min.js` - 백그라운드 PDF 처리 워커
- **용도**: PDF 파일 읽기 및 썸네일 생성
- **버전**: 4.6.82

### PDF-lib 
- **경로**: `pdf-lib/`
- **파일들**:
  - `pdf-lib.min.js` - PDF 생성 및 조작 라이브러리
- **용도**: PDF 파일 생성, 합치기, 이미지를 PDF로 변환
- **버전**: 1.17.1

## 특징

- **완전한 로컬 동작**: 네트워크 연결 없이도 모든 기능 사용 가능
- **개인정보 보호**: 파일이 외부 서버로 전송되지 않음
- **빠른 로딩**: CDN 의존성 없이 즉시 라이브러리 로드

## 업데이트 방법

라이브러리를 업데이트하려면:

```bash
# PDF.js 업데이트
curl -o pdfjs-dist/build/pdf.min.mjs https://cdn.jsdelivr.net/npm/pdfjs-dist@latest/build/pdf.min.mjs
curl -o pdfjs-dist/build/pdf.worker.min.js https://cdn.jsdelivr.net/npm/pdfjs-dist@latest/build/pdf.worker.min.js

# PDF-lib 업데이트  
curl -o pdf-lib/pdf-lib.min.js https://cdn.jsdelivr.net/npm/pdf-lib@latest/dist/pdf-lib.min.js
```