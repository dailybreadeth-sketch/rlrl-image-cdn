# RLRL Image CDN — 레알레알 이미지 에셋 허브

> 레알레알(RLRL) 로스카 샴푸 · 헤드스킨 상세페이지용  
> **이미지를 같은 이름으로 덮어쓰기하면 연결된 모든 상세페이지가 자동 갱신됩니다.**

---

## 📁 폴더 구조

```
images/
  shampoo/          ← 로스카 샴푸 이미지
    shampoo_hero_01.jpg
    shampoo_hero_02.jpg
    shampoo_nukki_01.png
    shampoo_detail_01.jpg
    shampoo_texture_01.jpg
  head-skin/        ← 로스카 헤드스킨 이미지
    headskin_hero_01.jpg
    headskin_nukki_01.png
    headskin_ritual_01.jpg
  brand/            ← 레알레알 브랜딩 에셋
    brand_logo_dark.svg
    brand_logo_light.svg
    brand_hero_campaign.jpg
    brand_manifesto_bg.jpg
```

---

## ⚡ 이미지 교체 방법

### 방법 A — GitHub 웹에서 직접 교체 (가장 간단)
1. GitHub 레포지토리의 `images/shampoo/` 폴더로 이동
2. 교체할 파일을 클릭 → 우측 상단 **[연필 아이콘]** 클릭
3. **Upload files**에서 같은 이름의 새 파일 업로드 → Commit

### 방법 B — 로컬에서 교체 후 Push
```bash
# 파일 복사 (같은 이름으로 덮어쓰기)
cp /새이미지경로/shampoo_hero_01.jpg ./images/shampoo/shampoo_hero_01.jpg

# 깃허브에 Push
git add .
git commit -m "feat: 샴푸 히어로 이미지 교체"
git push
```

---

## 🔗 상세페이지에 연결하는 방법

Vercel 배포 완료 후 아래 형식으로 상세페이지 HTML에 삽입:

```html
<!-- 샴푸 히어로컷 -->
<img src="https://[your-project].vercel.app/images/shampoo/shampoo_hero_01.jpg" alt="로스카 샴푸 히어로">

<!-- 캐시 문제 발생 시 버전 파라미터 추가 -->
<img src="https://[your-project].vercel.app/images/shampoo/shampoo_hero_01.jpg?v=2" alt="로스카 샴푸">
```

---

## 🔒 CORS 설정
`vercel.json`에 `Access-Control-Allow-Origin: *` 헤더가 설정되어 있어  
외부 쇼핑몰(자사몰, HTML 편집 지원 채널)에서 자유롭게 불러올 수 있습니다.

---

*Managed by 레알레알 (주)에브리먼데이 · Less Is Natural™*
