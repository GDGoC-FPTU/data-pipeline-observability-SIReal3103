# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600065
**Name:** Hoang Hiep
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9/10 | Ket qua hop ly vi du lieu clean co category chuan va gia tri gia dung. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 3/10 | Ket qua sai ngu canh mua sam vi outlier va du lieu nhiem doc lam agent uu tien gia lon nhat. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung garbage data, agent bi anh huong boi nhieu loi chat luong du lieu cung luc. Ban ghi duplicate ID lam mo ho quan he giua san pham va ban ghi goc, khieu model retrieval kho xac dinh dau la thong tin tin cay. Truong `price` co wrong data type nhu "ten dollars" co the gay loi parse hoac bi bo qua khong nhat quan. Gia tri outlier "Nuclear Reactor = 999999" lam lech logic chon san pham tot nhat theo gia, dan den goi y phi thuc te. Ngoai ra null values va category khong day du lam giam kha nang loc theo nganh hang, khien truy van electronics de bi tra ket qua sai.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Prompt tot chi phat huy khi du lieu dau vao dung, day du va nhat quan. Neu data bi nhiem doc, model van co the tra loi rat tu tin nhung sai ban chat. Vi vay trong he thong AI, data quality la lop phong thu dau tien truoc khi toi uu prompt.
