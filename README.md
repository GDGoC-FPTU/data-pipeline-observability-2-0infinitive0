[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112905&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** emiyashiro2002@gmail.com
**Name:** Nguyễn Hữu Đức

---

## Mo ta

Bài lab này xây dựng một Data Pipeline (ETL) đơn giản để trích xuất dữ liệu từ file JSON, kiểm tra tính hợp lệ của dữ liệu (validation), biến đổi dữ liệu (chuyển đổi đơn vị tiền tệ), và lưu kết quả vào file CSV. Ngoài ra, bài lab còn minh họa tầm quan trọng của Data Observability thông qua việc thực hiện Stress Test bằng cách chạy AI Agent với dữ liệu sạch (clean data) và dữ liệu rác (garbage data) để quan sát sự khác biệt trong kết quả của Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Chạy thử nghiệm AI Agent với dữ liệu sạch và dữ liệu rác
python agent_simulation.py
```

---

## Cau truc thu muc

```text
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Quá trình ETL chạy thành công trên file `raw_data.json`.
- **Số lượng bản ghi hợp lệ đã xử lý và lưu thành công:** 3 records.
- **Số lượng bản ghi bị loại do không hợp lệ:** 2 records.
- Trong quá trình chạy Agent Simulation (Stress Test):
  - **Với dữ liệu sạch (Clean Data):** Agent đưa ra quyết định hợp lý (Laptop at $1200).
  - **Với dữ liệu rác (Garbage Data):** Agent bị nhiễu và đưa ra quyết định vô lý (Nuclear Reactor at $999999).
  - Kết quả này nhấn mạnh tầm quan trọng của Data Quality và Data Observability đối với các hệ thống có sử dụng Machine Learning hay AI Agents.
