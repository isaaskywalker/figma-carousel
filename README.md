# Figma Carousel

> **재배포 금지 — 이 저장소의 스킬·문서·설정 양식을 저작자의 사전 허락 없이 재업로드, 재판매하거나 다른 배포물에 포함해 배포할 수 없습니다. 수정본의 재배포도 금지합니다.**
>
> 사용을 위한 다운로드·설치와 원본 저장소 링크 공유는 가능합니다. 공유할 때는 이 저장소의 원본 링크를 이용해 주세요.


사용자가 작성한 제작 양식과 자신의 Figma 템플릿으로 캐러셀을 만드는 Codex 스킬입니다. 원본을 복제해 문구와 사진을 적용하고, 장별 ID로 부분 수정을 지원합니다.


## 설치


```bash
git clone https://github.com/isaaskywalker/figma-carousel.git
cd figma-carousel
```


Codex에서 이 폴더를 열거나 아래처럼 스킬 설치를 요청하세요.


```text
$skill-installer로 https://github.com/isaaskywalker/figma-carousel/tree/main/.agents/skills/figma-carousel 를 설치해줘.
```


Codex와 Figma 연결 및 대상 파일의 편집 권한이 필요합니다.


## 시작 전 필수: 제작 양식 작성


**제작을 시작하기 전에 [제작 양식](.agents/skills/figma-carousel/references/intake-form.md)을 작성해 주세요.** 양식을 `carousel-brief.local.md`로 복사해 작성하거나, 항목별 답변을 Codex 대화에 입력합니다. 미작성 항목은 스킬이 확인하며, 필수 입력이 완료되기 전에는 원고 생성·템플릿 복제·편집을 시작하지 않습니다.


양식에는 주제, 독자, 문체, 장수와 구성, 템플릿 위치·이름, 폰트·크기·줄 수, 레이아웃, 효과 처리, 사진 및 출처 기준을 직접 지정합니다. 효과는 유지·제거·직접 지정 중 선택합니다. 값이 없는 경우 이전 사용자의 설정으로 채우지 않습니다.
