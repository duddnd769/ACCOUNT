# account_projec!

### 📌 요구사항
- 은행 이름: SC은행
- 속성: 예금주, 계좌번호, 잔액
- 생성자에서 예금주와 초기 잔액을 입력받음
- 계좌번호 형식: 3자리-2자리-6자리 (랜덤 생성)

---

### 🧩 Account 클래스 코드

```python
import random

class Account:
    def __init__(self, owner, balance):
        self.bank = "SC은행"
        self.owner = owner
        self.balance = balance
        self.account_number = self.create_account_number()

    def create_account_number(self):
        part1 = random.randint(100, 999)
        part2 = random.randint(10, 99)
        part3 = random.randint(100000, 999999)
        return f"{part1}-{part2}-{part3}"

acc = Account("정영웅", 1000000)

print(acc.bank)
print(acc.owner)
print(acc.account_number)
print(acc.balance)


