# 🎓 GradeBook — 학생 성적 관리 프로그램

> Python 패키지 예제 프로젝트  
> 평균 계산, 학점 산출, CSV 파일 입출력, CLI 실행 기능을 포함한 **학생 성적 관리 프로그램**

---

## 📁 프로젝트 구조

```
project_root_pkg/
├─ gradebook/                  ← 패키지 루트
│  ├─ __init__.py              ← 패키지 초기화 (버전, 공개 객체 정의)
│  ├─ __main__.py              ← 진입점 (python -m gradebook 실행 가능)
│  ├─ cli.py                   ← 명령행 인터페이스 (CLI)
│  ├─ models.py                ← Student, GradeBook 클래스
│  ├─ utils.py                 ← 평균, 학점 계산 함수
│  └─ io/                      ← 입출력 관련 하위 패키지
│     ├─ __init__.py
│     └─ csvio.py              ← CSV 파일 입출력 기능
└─ tests/
   └─ test_utils.py            ← unittest 예시 (utils 함수 테스트)
```

---

## 🚀 실행 방법

### 1️⃣ 패키지 실행
`__main__.py`가 포함되어 있으므로, 패키지를 직접 실행할 수 있습니다.

```bash
# project_root_pkg 디렉터리 위치에서 실행
python -m gradebook
```

실행 예시:
```
📘 GradeBook CLI 실행 중...
⚠️  students.csv 파일이 없습니다. 기본 데이터를 사용.
전체 반 평균 점수: 80.00

Alice: 평균=89.0, 학점=A
Bob:   평균=71.0, 학점=C
```

---

### 2️⃣ CSV 파일 사용 (선택 사항)
`students.csv` 파일이 같은 디렉터리에 있으면 자동으로 데이터를 불러옵니다.  
CSV 형식은 다음과 같습니다.

```csv
name,score1,score2,score3
Alice,90,85,92
Bob,70,75,68
Charlie,88,92,81
```

---

### 3️⃣ 단위 테스트 실행

`unittest` 모듈로 유틸리티 함수(`mean`, `letter_grade`)를 검증할 수 있습니다.

```bash
# tests 폴더에서 테스트 실행
python -m unittest tests/test_utils.py -v
```

출력 예시:
```
test_letter_grade (tests.test_utils.TestUtils) ... ok
test_mean (tests.test_utils.TestUtils) ... ok

----------------------------------------------------------------------
Ran 2 tests in 0.001s

OK
```

---

## 📦 주요 모듈 설명

| 모듈 | 설명 |
|------|------|
| `utils.py` | 평균 및 학점 계산 함수 정의 |
| `models.py` | `Student`, `GradeBook` 클래스 정의 |
| `cli.py` | 터미널용 실행 인터페이스 (CLI) |
| `io/csvio.py` | CSV 파일 입출력 기능 |
| `__main__.py` | CLI 실행 진입점 |
| `tests/test_utils.py` | `unittest` 기반 테스트 코드 |

---

## 🧩 예시 코드

```python
from gradebook.models import Student, GradeBook

# 학생 추가
alice = Student("Alice", [90, 85, 92])
bob = Student("Bob", [70, 75, 68])

# 성적부 생성
gb = GradeBook()
gb.add_student(alice)
gb.add_student(bob)

# 출력
print("전체 평균:", gb.average())
for s in gb.students:
    print(s.name, s.average(), s.grade())
```

---

## 🧠 버전 정보
- Version: **1.0.0**
- Python: **3.8+**
- License: MIT (or 자유롭게 수정 가능)

---

## ✨ 작성자
**오재언 (Oh Jae-Eon)**  
📚 Example Educational Project for Learning Python Package Structure
