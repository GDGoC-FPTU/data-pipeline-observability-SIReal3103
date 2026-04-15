[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574176&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** email@example.com
**Name:** (Dien ten cua ban)

---

## Mo ta

Lab nay xay ETL pipeline don gian tu file JSON -> CSV gom 4 buoc Extract, Validate, Transform, Load. 
Sau khi tao bo du lieu clean, minh tao them bo garbage data va chay stress test agent de quan sat tac dong cua data quality den chat luong cau tra loi.

---

## Cach chay (How to Run)

### Prerequisites
```bash
python3 -m venv venv
source venv/bin/activate
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Raw data: 5 records
- Sau validation: 3 records hop le, 2 records bi loai (`price <= 0` va `category` rong)
- Output: tao `processed_data.csv` voi cac cot `discounted_price` va `processed_at`
- Stress test:
  - Clean data: Agent tra loi hop ly (Laptop - $1200)
  - Garbage data: Agent bi lech do outlier (Nuclear Reactor - $999999)
