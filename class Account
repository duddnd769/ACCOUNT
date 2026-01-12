import random

class Account:

    # Q2. 클래스 변수 (생성된 계좌 개수 저장)
    account_count = 0

    # Q1. Account 클래스 (은행이름, 예금주, 계좌번호, 잔액)
    def __init__(self, owner, balance):
        self.bank = "SC은행"
        self.owner = owner
        self.balance = balance
        self.account_number = self._create_account_number()

        self.deposit_count = 0
        self.deposit_log = []
        self.withdraw_log = []

        Account.account_count += 1

    # Q1. 계좌 개설 메서드 (계좌번호 랜덤 생성)
    def _create_account_number(self):
        return f"{random.randint(100,999)}-{random.randint(10,99)}-{random.randint(100000,999999)}"

    # Q3. 클래스 변수 출력 메서드
    @classmethod
    def get_account_num(cls):
        print(cls.account_count)

    # Q4. 입금 메서드 (1원 이상만 가능)
    def deposit(self, amount):
        if amount < 1:
            return
        self.balance += amount
        self.deposit_count += 1
        self.deposit_log.append(amount)

        # Q7. 입금 5회마다 이자 지급 (1%)
        if self.deposit_count % 5 == 0:
            interest = int(self.balance * 0.01)
            self.balance += interest

    # Q5. 출금 메서드 (잔액 이상 출금 불가)
    def withdraw(self, amount):
        if amount > self.balance:
            return False
        self.balance -= amount
        self.withdraw_log.append(amount)
        return True

    # Q6. 정보 출력 메서드 (잔고 세자리 콤마)
    def display_info(self):
        print(
            f"(은행이름: {self.bank}, 예금주: {self.owner}, "
            f"계좌번호: {self.account_number}, 잔고: {self.balance:,}원)"
        )

    # Q10. 입금/출금 내역 출력 메서드
    def show_history(self):
        print("입금 내역:", self.deposit_log)
        print("출금 내역:", self.withdraw_log)


# Q8. 여러 객체 생성
accounts = [
    Account("정영웅", 1_000_000),
    Account("홍길동", 500_000),
    Account("김철수", 2_000_000)
]

# Q9. 잔고 100만원 이상 고객 정보 출력
for acc in accounts:
    if acc.balance >= 1_000_000:
        acc.display_info()
