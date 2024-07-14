# yaman-doujin-game-manager
동인 게임을 로컬 경로와 매핑하여 관리하는 도구

# 주요 기능

<details>
<summary style="font-weight: bold;">로컬 폴더 스캔 & 작품 매핑</summary>

- 로컬 폴더를 스캔하고, 작품 정보를 가져와서 매핑합니다.
  - 현재 지원중인 사이트: DLSITE, GETCHU, FANZA

![1](https://github.com/user-attachments/assets/0ebfd47b-7b4e-49c8-b120-5238961895e4)
</details>


<details>
<summary style="font-weight: bold;">작품 검색 & 관리</summary>

- 작품들을 쉽게 검색하고 관리할 수 있습니다.

![5](https://github.com/user-attachments/assets/24f330ca-0dbc-4397-8f77-657ec2418c96)
![6](https://github.com/user-attachments/assets/04a8e005-9178-48ad-b582-0153fc50752c)
</details>

<details>
<summary style="font-weight: bold;">세이브 검색 & 다운로드</summary>

- 세이브를 자동으로 검색하고 다운로드 할 수 있습니다.

![화면 캡처 2024-07-14 205629](https://github.com/user-attachments/assets/fb432422-a7fb-4d0b-96e6-91f38651a323)
</details>

<details>
<summary style="font-weight: bold;">치트 자동 적용</summary>

- 폴더 안에 게임이 압축 해제된 상태로 있는 경우 자동으로 치트를 적용합니다.
- 현재 RPG-VX, RPG-VX-ACE, RPG-MV, RPG-MZ 만 지원중입니다.

![화면 캡처 2024-07-14 205756](https://github.com/user-attachments/assets/a8d52e95-059f-4e87-9bae-d25c90e0c399)
</details>


# 지원 예정

- 작품 정보 자동 번역
- 경로 삭제(휴지통 & 영구 삭제)/이동/이름변경
- 작품 삭제
- 사용되지 않는 라벨/그룹 정리, 존재하지 않는 경로 정리

# 기본 사용법
## 시작하기 전에

- 이 프로그램은 일본 IP 로 바꿔주는 **VPN 을 사용**하기를 강력하게 권장합니다. (DPI 우회 프로그램이 아닌 VPN)
- 일부 사이트(Fanza)에서는 한국 IP 로는 아예 접근할 수 없는 경우도 있으며, 상당수의 작품이 한국 IP 로는 접근 불가능합니다.
- 세이브 검색에서 구글 검색을 사용하는데, 한국 IP 로는 성인인증을 하지 않으면 검색이 제대로 되지 않아서 해당 기능을 사실상 사용할 수 없습니다.
- 추가적으로 작품 정보를 가져오거나, 구글 검색 및 번역을 할 때 단시간에 많은 요청을 보내는 경우가 있어서 IP 가 차단될 수도 있습니다.
  - 현재 버전에서는 구글 번역 기능은 추가하지 않았기 때문에 구글쪽에 요청이 몰릴 가능성은 없습니다.

## 다운로드 및 실행

- [release](https://github.com/paramonos/yaman-doujin-game-manager/releases/latest) 에서 압축 파일 다운로드 및 해제합니다.
- 압축 해제된 폴더에서 `yaman.bat` 을 실행합니다.

## 작품 등록을 위한 폴더 스캔
### 작품이 매핑되는 조건
- 모든 작품은 폴더 단위로 관리된다고 가정합니다.
- 폴더 이름에 작품을 매핑시킬 수 있는 특정 패턴이 존재해야합니다. (ex: `.... [RJ000000]`)
- Getchu, Fanza 의 경우 ID 구분을 위해 아래와 같이 작품 코드를 GC, FZ 접두어를 붙여서 표현해야 합니다.
  - `... [GC000000]` `... [FZd_000000]`
- 스캔은 지정한 폴더 바로 하위에 존재하는 폴더들을 대상으로 진행됩니다.

### 폴더 스캔 실행

- 작업 - 스캔작업 탭에서 폴더 스캔을 실행할 수 있습니다.
- 스캔할 폴더 경로를 `대상 부모 디렉토리` 에 입력하고 `실행` 을 클릭합니다.

<details>
<summary style="font-weight: bold;">이미지 보기</summary>
  
**작업 - 스캔작업 탭**

![1](https://github.com/user-attachments/assets/397d6e2f-120b-459b-be46-e2fa118462c2)

**예시 폴더 구조**

![2](https://github.com/user-attachments/assets/51d2ace6-5e00-4084-b9e4-bfa5295a9823)

**폴더 입력 시 실행 버튼이 생김**

![3](https://github.com/user-attachments/assets/d3d06eba-d8fe-4e96-976b-8ce80af7dda8)
</details>

- 실행 후 "작업 - 콘솔" 탭에서 작업 진행 현황을 확인할 수 있습니다.

<details>
<summary style="font-weight: bold;">이미지 보기</summary>

![4](https://github.com/user-attachments/assets/c234a887-48e0-4d47-94f4-7d44ba3bd256)
</details>

### 작품 검색 및 관리

- 작품 정보를 자동으로 가져오는데 실패한 경우, 해당 작품은 경고(warning) 표시가 붙은 채로 추가됩니다.
  - 작품이 사이트에서 내려간 경우가 일반적입니다. 간혹 작품이 살아있는데 내부 버그로 정보를 가져오는데 실패할 수도 있습니다.
<details>
<summary style="font-weight: bold;">이미지 보기</summary>
  
![화면 캡처 2024-07-14 213121](https://github.com/user-attachments/assets/d7f84dd3-3260-4c07-b43d-4942b68b1e56)
  
</details>

- 이런 경우 수동으로 작품 정보를 추가해줄 수 있습니다.
  - 작품을 클릭하여 상세 정보를 띄웁니다.
  - 작품이 "일반 작품" 으로 되어 있는 경우, "커스텀 라벨" 과 "경로", "메모" 밖에 수정할 수 없습니다.
  - 따라서 우선 "일반 작품" 을 클릭하여 커스텀 작품으로 바꿔줍니다.
  - 그 후 타이틀, 그룹, 라벨, 작품 정보 등을 클릭하여 수정하고, 필요한 경우 이미지를 드래그하여 업로드 합니다.
  - 그룹, 라벨의 경우 원하는 이름의 그룹/라벨이 존재하지 않는다면 직접 입력하여 생성할 수 있습니다.
  - 모든 정보를 입력했다면 "경고" 를 클릭하여 해당 작품은 관리가 되어 경고 표시가 필요없음을 표시합니다.
  - **추가 주의사항) "커스텀 작품" 상태를 해제하는 경우 작품 정보를 다시 가져오는 작업을 실행할 경우 입력해둔 정보가 사라질 수 있습니다**

<details>
<summary style="font-weight: bold;">이미지 보기</summary>

**상세 탭에서 커스텀 작품으로 전환합니다.**

![화면 캡처 2024-07-14 213510](https://github.com/user-attachments/assets/b6e7f6d0-e290-49e3-b16f-5a5e5db15f07)

**그 후 제목, 그룹, 라벨 등도 편집이 가능해집니다.**

![화면 캡처 2024-07-14 213510](https://github.com/user-attachments/assets/cafbe8fd-94c9-434c-ad30-da30a21f07e0)
![화면 캡처 2024-07-14 213520](https://github.com/user-attachments/assets/14da00ca-4400-4353-ae00-7dd89b07b190)
![화면 캡처 2024-07-14 213535](https://github.com/user-attachments/assets/37b276ba-bdb4-42d0-9a2b-3a2045aa42e3)
![화면 캡처 2024-07-14 213619](https://github.com/user-attachments/assets/076cb30e-91d0-49e1-96b6-87cc74ee35bf)

**마음에 드는 그룹/라벨이 없는 경우 임의로 생성할 수 있습니다**

![화면 캡처 2024-07-14 213712](https://github.com/user-attachments/assets/61177212-3b1b-4df3-80a3-2487dedbb7c4)
![화면 캡처 2024-07-14 213719](https://github.com/user-attachments/assets/8b06625a-40e2-4beb-9f88-729daa919abd)

**입력이 끝난 경우 경고 표시를 해제하여 관리가 필요하지 않은 작품임을 구분할 수 있게 합니다**

![화면 캡처 2024-07-14 213825](https://github.com/user-attachments/assets/e6dcd8b7-794a-4454-b7c7-6fe6c25754e0)

</details>

**커스텀 작품**
- "커스텀 작품" 으로 지정된 경우, 모든 작품 정보 자동 등록 작업에서 제외됩니다.
- 사용자가 입력한 정보가 다시 덮어씌워지지 않기를 바라는 경우 커스텀 작품으로 표시해주세요
  - 참고) "커스텀 라벨", "메모" 는 일반 작품에서도 편집 가능하며 덮어씌워지지 않는 속성들입니다.

# 추가 사용법
## 일반 브라우저에서 사용

- 프로그램이 켜져있는 상태일 때 크롬 등의 브라우저에서 http://localhost:8082 로 접속하면 브라우저에서도 사용이 가능합니다.

## 폴더 스캔 추가 기능 사용

- `경로 이동`: 폴더 스캔은 단순히 해당 폴더만 스캔하는 것 뿐만 아니라 스캔 후 작품이 등록된 폴더들을 다른 폴더로 이동시키도록 할 수도 있습니다.
- `커스텀 작품 등록`: 작품 ID 가 기재되지 않은 폴더도 무시하지 않고 작품으로 등록하도록 할 수 있습니다. (아예 판매중인 사이트가 없는 게임들)
- `작품 기본값 설정`: 같은 부류의 작품을 등록할 때 그 작품들에 모두 같은 속성을 주고 싶을 때 사용합니다.

<details>
<summary style="font-weight: bold;">사용 예시</summary>

**작업 전 폴더 구조**

![화면 캡처 2024-07-14 220337](https://github.com/user-attachments/assets/54ba547b-ab83-4dfd-8141-f92b17dd8982)
![화면 캡처 2024-07-14 220347](https://github.com/user-attachments/assets/70892187-c083-48b8-acdf-08317d7094c3)


**스캔 설정**

![화면 캡처 2024-07-14 220301](https://github.com/user-attachments/assets/92a76bfa-5fac-42f9-93df-0bc972fec134)

**작업 후**
**코드가 없는 작품이 등록됨**

![화면 캡처 2024-07-14 220447](https://github.com/user-attachments/assets/58d97421-6bcd-421e-adb3-a996b1bb2c37)

**폴더가 이동됨**

![화면 캡처 2024-07-14 220534](https://github.com/user-attachments/assets/93f3c57e-c1d4-45d3-b0d3-acb7e0e00dcf)

</details>

## 파라미터 템플릿

- 현재 설정한 작품 옵션들을 나중에도 사용할 수 있도록 저장해두는 기능입니다.
- "템플릿으로 저장" 을 클릭하여 추가할 수 있습니다.
- 저장된 템플릿을 변경하고 싶은 경우, 설정을 변경한 뒤 동일한 이름으로 "템플릿으로 저장"을 하면 덮어씌워집니다.
- 저장된 템플릿을 클릭하면 해당 템플릿대로 값을 자동으로 채워줍니다.

<details>
<summary style="font-weight: bold;">이미지 보기</summary>

![화면 캡처 2024-07-14 215945](https://github.com/user-attachments/assets/eb361f0c-e876-49c9-8e4d-f8e35cdbfad6)
![화면 캡처 2024-07-14 220000](https://github.com/user-attachments/assets/46e17065-100f-4473-9770-cf052f182e0a)

</details>

# 주의사항
## 보안 관련
- 프로그램이 내부적으로 서버를 동작시키기 때문에 8082 포트가 노출되지 않도록 방화벽 및 공유기 설정을 확인해주세요.
- 로컬 IP 가 아닌 IP 의 요청은 무시하도록 기본적인 구성은 해두었습니다.

## DB 백업
- DB 는 주기적으로 백업해두기를 권장합니다.
