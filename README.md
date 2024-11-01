# java-lotto-precourse

# 우아한 프리코스 3주차 미션: 로또

---
# 입력

### 첫 번째 입력 - 로또 구입 금액

- 구입 금액은 1,000원 단위
- 1,000원으로 나누어 떨어지지 않으면 → 예외처리

### 두 번째 입력 - 당첨 번호

- 번호는 쉼표(,)를 기준으로 구분
- 총 6개의 숫자를 입력받는다(한 줄로 + 쉼표로 구분된)

### 세 번째 입력 - 보너스 번호

- 숫자 단 하나만 입력 받음

# 출력

### 첫 번째 출력 - N개의 로또 구매

- 입력된 로또 구입 금액만큼의 로또 구입
- N개라 가정
    - N개를 구입했습니다.
    - N개의 줄 만큼 [숫자, 숫자, 숫자, 숫자, 숫자, 숫자] 로또 번호 출력

### 두 번째 출력 - 결과

- 결과 시작

    ```json
    당첨 통계
    ---
    ```

- 이후 구입한 로또의 번호와 당첨번호의 일치 개수별 당첨 개수 출력

    ```json
    3개 일치 (5,000원) - ?개
    4개 일치 (50,000원) - ?개
    5개 일치 (1,500,000원) - ?개
    5개 일치, 보너스 볼 일치 (30,000,000원) - ?개
    6개 일치 (2,000,000,000원) - ?개
    ```

- 마지막으로 수익률 출력
---
# 필요한 기능
- [ ] 입력된 로또 구매 금액에 따른 로또 구매 개수 설정 기능
- [ ] 구매된 로또들에 각각 6개의 랜덤한 숫자를 부여하는 기능
- [ ] 입력된 당첨 번호를 당첨 번호로 설정하는 기능
- [ ] 입력된 보너스 번호를 보너스 번호로 설정하는 기능
- [ ] 당첨 번호와 각 로또들의 번호를 비교하여 일치하는 숫자의 개수를 체크하는 기능
- [ ] 보너스 번호와 각 로또들의 번호를 비교하여 일치하는 숫자가 있는지 체크하는 기능
- [ ] 일치한 숫자 3개 이상부터는 N개 일치한 로또의 개수를 카운트 하는 기능
- [ ] 당첨번호와 일치하는 번호 개수 + 보너스 번호 일치하는 숫자 유무(boolean)으로 결과내는 기능
- [ ] 각 일치한 숫자 개수별 당첨금 과 카운트된 개수를 종합하여 수익률을 계산하는 기능

## 메인 기능 플로우

`반복문(전체 로또 개수){`

`메서드(당첨 번호와 일치하는 번호의 개수를 체크하는 메서드)(반환값은 일치하는 번호 개수)`

`메서드(보너스 번호와 일치하는 숫자 있는지 체크하는 메서드)(반환값은 불린)`

`메서드(위의 두 메서드의 결과에 따른 로또 번호 일치하는 숫자 개수 카운트하는 메서드)(반환값 X)`

`(이때 6개인 경우와 5개+보너스 숫자인 경우를 분리해서 기록해야 함)`

`}`

---
# 예외 상황

- 공통
    - 빈 문자열
- 구입금액 입력
    - 구입 금액이 1,000원 단위로 떨어지지 않는 경우
- 당첨 번호 입력
    - 6개 이상의 숫자를 입력한 경우
    - 숫자와 구분자 외의 문자가 포함된 경우 = 구분자로 콤마가 사용되지 않은 경우
    - 구분자 사이가 비어있는 경우
    - 당첨번호가 1~45의 범위를 벗어나는 경우
    - 중복된 번호가 입력되는 경우 → set을 이용해 담은 후 개수가 6개인지 체크하면 될 듯하다
- 보너스 번호 입력
    - 숫자 이외의 문자를 입력하는 경우
    - 숫자를 하나 이상 입력하는 경우
    - 입력된 숫자가 1~45의 범위를 벗어나는 경우
    - 당첨 번호와 중복된 번호인 경우 → 이건 set에 담지 말고 따로 구분해야 하기에, 입력받은 값을 당첨번호 set과 비교하는게 필요할 듯하다
---

# 이번 미션에서 신경쓸 것

- 변하지 않는 변수에 final을 붙여줄 것
- getter를 지양할 것
- 값을 하드코딩 하지 않을 것