# yaman-doujin-game-manager
동인 게임을 로컬 경로와 매핑하여 관리하는 도구

# 주요 기능

<details>
<summary style="font-weight: bold;">로컬 폴더 스캔 & 작품 매핑</summary>

- 로컬 폴더를 스캔하고, 작품 정보를 가져와서 매핑합니다.
  - 현재 지원중인 사이트: DLSITE, GETCHU, FANZA

![1](https://github.com/user-attachments/assets/0ebfd47b-7b4e-49c8-b120-5238961895e4)
![화면 캡처 2024-07-27 192034](https://github.com/user-attachments/assets/66937287-9dbf-44d9-b1b4-e93c8177bbdc)


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
- MEGA 링크의 경우 따로 [MEGACmd](https://mega.io/ko/cmd) 프로그램을 설치해야 자동 다운로드가 가능합니다.

![화면 캡처 2024-07-14 205629](https://github.com/user-attachments/assets/fb432422-a7fb-4d0b-96e6-91f38651a323)
</details>

<details>
<summary style="font-weight: bold;">치트 자동 적용</summary>

- 폴더 안에 게임이 압축 해제된 상태로 있는 경우 자동으로 치트를 적용합니다.
- 현재 RPG-VX, RPG-VX-ACE, RPG-MV, RPG-MZ 만 지원중입니다.

![화면 캡처 2024-07-14 205756](https://github.com/user-attachments/assets/a8d52e95-059f-4e87-9bae-d25c90e0c399)
</details>

<details>
<summary style="font-weight: bold;">영문 경로에서만 실행 가능한 게임 대응</summary>

- 원본 게임 폴더를 임시 폴더로 복사(포크) 하고 포크에서 생긴 변경사항을 원본 게임으로 다시 병합하는 기능입니다.

![화면 캡처 2024-07-21 015838](https://github.com/user-attachments/assets/fb59d09e-49fc-4f6d-9bd1-3b2fb473714f)
![화면 캡처 2024-07-21 015916](https://github.com/user-attachments/assets/6b4fc26c-6c98-4452-a23e-26e84ef2161c)
![화면 캡처 2024-07-21 015933](https://github.com/user-attachments/assets/c054eba8-1fc3-4109-9693-882136ab55b7)


</details>

# 지원 예정

- 세이브 파일 다운로드 후 자동 적용
- 사라진 작품 혹은 커스텀 작품 정보 자동 채우기 (썸네일)
- 자동 압축 해제
- 작품 정보 자동 번역
- 경로 삭제(휴지통 & 영구 삭제)/이동/이름변경
- 작품 삭제
- 사용되지 않는 라벨/그룹 정리, 존재하지 않는 경로 정리

# 기본 사용법
## 시작하기 전에

- 이 프로그램은 일본 IP 로 바꿔주는 VPN 을 사용하기를 권장합니다. (DPI 우회 프로그램이 아닌 VPN)
  - 일부 사이트(Fanza)에서는 한국 IP 로는 아예 접근할 수 없는 경우도 있으며, DLSITE AI 작품 등은 한국 IP 로는 접근 불가능합니다.

## 다운로드 및 실행

- [release](https://github.com/paramonos/yaman-doujin-game-manager/releases/latest) 에서 압축 파일 다운로드 및 해제합니다.
- 압축 해제된 폴더에서 `yaman.bat` 을 실행합니다.

## 작품 등록을 위한 폴더 스캔
### 작품이 매핑되는 조건
- 모든 **작품은 폴더 단위로 관리된다고 가정**합니다.
  - **압축 파일의 경우 자동으로 같은 이름의 폴더로 감싸서 관리**합니다.
- 폴더 이름에 작품을 매핑시킬 수 있는 특정 패턴이 존재해야합니다. (ex: `.... [RJ000000]`)
- Getchu, Fanza 의 경우 ID 구분을 위해 아래와 같이 작품 코드를 GC, FZ 접두어를 붙여서 표현해야 합니다.
  - `... [GC000000]` `... [FZd_000000]`
  - 작품 ID 를 감싸는 문자(기본 '[]')는 바꿀 수 있지만, 현재 ID 접두사를 임의로 변경하는건 불가능합니다.
  - (추가 사용법 참고)
- 스캔은 지정한 폴더 바로 하위에 존재하는 폴더들을 대상으로 진행됩니다.

### 방법 1: 폴더 동기화

- 작업 - 폴더 동기화 탭에서 관리 대상 폴더를 등록하고 동기화 시킬 수 있습니다.
- 동기화 폴더를 등록한 후, 원하는 동기화 옵션을 설정합니다.
- 그 후, 동기화 폴더 스캔 작업을 실행하여 변경된 경로들을 추출하고, 동기화 적용 작업을 실행하여 실제 동기화를 진행합니다.

**옵션**

- 깊이: 스캔할 깊이를 제한합니다.
- 깊이 고정: 작품들이 폴더를 기준으로 특정 깊이에만 존재할 경우 사용할 수 있는 옵션입니다.
  - 활성화 시 해당 깊이의 경로들만 동기화 됩니다.
  - ID 매핑이 되지 않는 폴더가 모호하지 않기 때문에 커스텀 작품을 정확하게 추가할 수 있습니다.
  - 다음과 같은 폴더 구조를 가진 경우 유용합니다.
    - 동기화폴더/번역/작품1
    - 동기화폴더/번역/작품2
    - 동기화폴더/미번역/작품1
    - 동기화폴더/미번역/작품2
- 삭제된 경로 제거: DB 에 존재하는 경로들 중, 더이상 존재하지 않는 경로들을 자동으로 제거합니다.
- 압축 파일 감싸기: 압축 파일도 동기화 스캔 대상으로 취급합니다. 단, 압축 파일 동기화 시 압축 파일을 감싸는 폴더를 자동으로 생성합니다.
- 커스텀 작품 등록: 작품과 매치되지 않는 경로들도 커스텀 작품으로 추가합니다.
  - "깊이까지 검색" 옵션을 사용하는 경우 부적확한 경로들이 커스텀 작품으로 추가될 수 있습니다.

<details>
<summary style="font-weight: bold;">이미지 보기</summary>
  
**작업 - 폴더 동기화 탭 - 추가**

![화면 캡처 2024-07-27 191820](https://github.com/user-attachments/assets/c849bee7-b876-4664-8621-2b1af8950916)

![화면 캡처 2024-07-27 191949](https://github.com/user-attachments/assets/716721ba-d295-422f-90a4-21d0bb01c9fb)

**동기화 스캔 실행**

![화면 캡처 2024-07-27 192015](https://github.com/user-attachments/assets/0b78dcf3-fc65-4fb2-a94a-8937dde6c163)

**동기화 적용 실행**

![화면 캡처 2024-07-27 192034](https://github.com/user-attachments/assets/fc46dd56-c826-457a-a9d4-e8fd83a529ab)

![화면 캡처 2024-07-27 192113](https://github.com/user-attachments/assets/a59f89a9-fd54-49fe-b157-7b06f70dc085)

</details>

### 방법 2: 폴더 스캔 실행

- 작업 - 스캔작업 탭에서 폴더 스캔을 실행할 수 있습니다.
- 스캔할 폴더 경로를 `대상 부모 폴더` 에 입력하고 `실행` 을 클릭합니다.
- 해당 폴더 바로 아래에 있는 폴더만 스캔되며, 주로 스캔과 동시에 경로 이동을 시키고 싶은 경우 사용합니다.

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

## 설정 변경

- 설정은 `options.yaml` 파일을 수정하여 변경할 수 있습니다.
- 설정 변경이 필요한 경우 텍스트 에디터로 변경하세요.
- 아래 기술된 내용 외 설정은 변경하지 않는 것을 권장합니다.

### 데이터 경로

기본값으로 데이터가 저장되는 곳은 해당 프로그램의 `data` 폴더이며, 설정에서 변경할 수 있습니다.

```yaml
app:
  data:
    path:
      client: "client/doujin-manager-electron.exe"
      root: "./data" # 경로는 반드시 '/' 로 구분해서 넣으세요 (윈도우 탐색기 복사 시 '\' 주의)
```

### 작품 ID 패턴 변경

작품 ID 매핑 패턴은 정규표현식 형태로 변경할 수 있습니다.

- ex) 대괄호 없이 ID 만 매핑 `(?<id>RJ\d{6,}|VJ\d{6,}|BJ\d{6,})`
  - RJ000000, GC000000, ....
- ex) 대괄호를 소괄호로 변경 `\((?<id>RJ\d{6,}|VJ\d{6,}|BJ\d{6,})\)`
  - (RJ000000), (GC000000), ....
- 정규표현식 검사는 [다음과 같은 사이트](https://regex101.com/)들에서 확인할 수 있습니다.

단, 현재 Fanza 및 Getchu ID 접두어 (FZ, GC) 는 변경이 불가능합니다.

```yaml
app:
  data:
    ...
  config:
    ...
    provider-mapping:
      providers:
        dlsite:
          regex: '\[(?<id>RJ\d{6,}|VJ\d{6,}|BJ\d{6,})]' # 여기서 정규표현식 수정
          idPattern: '${id}'
        getchu:
          regex: '\[(?<id>GC\d{6,})]'
          idPattern: '${id}'
        fanza:
          regex: '\[(?<id>FZ[0-9a-zA-Z_]+)]'
          idPattern: '${id}'
```

## 치트 사용

### MV/MZ

MV/MZ 는 [이 링크](https://github.com/paramonos/RPG-Maker-MV-MZ-Cheat-UI-Plugin)의 치트를 사용합니다. 치트 사용법은 링크를 참고해주세요.

추가적으로, 해당 치트의 단축키나 기본 배속등을 수정해서 모든 게임에 적용하고 싶은 경우 다음과 같이 치트 설정 파일을 프로그램 데이터 폴더에 넣어주면 다음 치트 적용부터는 해당 설정이 그대로 적용됩니다.

- MV, MZ 모두 `{게임 폴더}/www/cheat-settings` 에 치트 설정이 저장됩니다.
- 이 폴더 안의 모든 파일들을 프로그램 폴더의 `cheat` 폴더를 만들어서 복사합니다.
- ex) 이 프로그램이 `C:/downloads/yaman` 에 설치되어 있는 경우, (즉 `yaman.bat` 파일이 해당 폴더에 있는 경우)
  - MV 설정의 경우: `C:/downloads/yaman/cheat/mv/cheat-settings` 폴더에 설정 파일 복사
  - MZ 설정의 경우: `C:/downloads/yaman/cheat/mz/www/cheat-settings` 폴더에 설정 파일 복사
    - **MZ 게임은 www 폴더가 추가적으로 필요합니다.**
- **위 설정파일에서 root 경로를 바꿨다면 해당 경로 기준으로 설정을 넣어주면 됩니다**

### VX ACE
- F8: 치트메뉴
- F9: 변수 조작

### VX
- F9: 치트 메뉴

## 세이브 검색 관련

세이브 검색 기능은 비공식 구글 검색 API 를 사용하는데, 해당 기능을 많이 사용하면 구글 측에서 캡차 입력을 요구합니다.
이런 경우 두 가지 방법 중 하나로 해결이 가능합니다.

1. VPN 으로 IP 변경
2. 직접 캡차를 해결하고 관련 정보를 프로그램에 입력
   - 해당 방법 사용 시 매우 짧은 주기로 구글에서 캡차 재입력 요구를 할 수 있습니다.

아래는 그 중 두 번째 방법에 대한 설명입니다.

### 구글 검색에 필요한 쿠키/헤더 얻어오기

1. 크롬 시크릿 탭을 엽니다. (`Ctrl + Shift + N`)
2. 시크릿 탭에서 크롬 개발자 도구를 엽니다. (`F12`)
3. 개발자 도구 네트워크 탭을 클립합니다.
4. 시크릿 탭에서 구글 접속 후 아무 단어나 검색합니다.
5. 개발자 도구 네트워크 탭에서 `search` 를 검색하고, `Fetch/XHR` 을 클릭하면 요청이 필터링 됩니다.
   - 일반적으로 2개의 요청이 필터링되며, 필터링 되는 요청이 없는 경우 `Fetch/XHR` 대신 `All` 을 클릭하여 `search` 를 검색합니다.
   - 요청이 검색되지 않으면 개발자 도구를 유지한 상태로 구글 검색 창을 새로고침합니다.
6. 필터링된 `search` 요청 중 가장 마지막 요청을 클릭하면, 오른쪽 `Headers` 탭에서 쿠키와 헤더를 확인할 수 있습니다.


<details>
<summary style="font-weight: bold;">이미지 보기</summary>

**개발자 도구 열기**

![1  debug mode](https://github.com/user-attachments/assets/169b7364-09f3-4385-a581-f0849ce7c2d1)

**아무 단어나 검색하기**

![2  search](https://github.com/user-attachments/assets/73d682e7-4ec7-450f-a121-8147f4cd02ea)

**개발자 도구 네트워크 탭 열어서 search 요청 검색**

![3  network](https://github.com/user-attachments/assets/5386620f-a9ea-4b2e-8702-033b50a16b09)

**쿠키 정보 확인 (`AEC=...`)**

![4  cookie](https://github.com/user-attachments/assets/65e8f7da-7a50-460a-b673-244211143edd)

**헤더 정보 확인**

![5  headers](https://github.com/user-attachments/assets/2f96161d-99d6-40af-9d19-2af5a64763e8)

</details>

### 얻어온 쿠키/헤더 프로그램에 입력

위에서 얻어온 쿠키와 헤더를 각각 프로그램에 입력합니다.

프로그램의 `설정 - 구글 설정` 탭으로 이동 후, 쿠키와 헤더 쪽에 각각 데이터를 입력합니다.

쿠키/헤더 테이블을 클릭하면 편집을 시작할 수 있습니다.

- 쿠키: 개발자 도구에서 `Cookie:` 에 대한 값을 드래그하여 복사 후 붙여넣기
- 헤더: 개발자 도구에서 `Downlink:` 에서부터 `User-Agent:` 의 값까지 전부 드래그하여 복사 후 붙여넣기
   - 반드시 `User-Agent:` 의 값까지 복사돼야 함

<details>
<summary style="font-weight: bold;">이미지 보기</summary>

**쿠키 입력**

![1  cookie 1](https://github.com/user-attachments/assets/7cf7d4bb-4008-4a2b-b15b-11383f98df29)

**헤더 입력**

![2  header](https://github.com/user-attachments/assets/cca39f7d-b728-4ec5-a82f-75e6aa13ffca)

**입력 후 다음과 같이 테이블이 나와야 함**

![3  result](https://github.com/user-attachments/assets/cd111839-c946-4993-aaee-c76b808d0767)

</details>

# 주의사항
## 보안 관련
- 프로그램이 내부적으로 서버를 동작시키기 때문에 8082 포트가 노출되지 않도록 방화벽 및 공유기 설정을 확인해주세요.
- 로컬 IP 가 아닌 IP 의 요청은 무시하도록 기본적인 구성은 해두었습니다.

## DB 백업
- DB 는 주기적으로 백업해두기를 권장합니다.
