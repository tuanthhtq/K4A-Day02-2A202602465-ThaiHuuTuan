# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Thái Hữu Tuấn
- Mã học viên: 2A202602465
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): lập trình viên web/ mobile
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem): setup/ hướng dẫn setup môi trường cho dự án, check thư viện đang dùng có cần nâng cấp hay không, tích hợp api vào web/app, đảm bảo giao diện responsive

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | tốn thời gian | không có tài liệu hướng dẫn setup môi trường cụ thể dẫn đến việc khi chạy dự án mobile trên máy mới có thể lỗi vì môi trường (modejs, java) không phù hợp | thành viên mới của dự án | 2 lần/ tháng, 60 phút mỗi lần sửa |
| 2 | ai có thể tốt hơn | khi thư viện cần được nâng cấp/ thay đổi/ thêm mới, dev phải đọc tài liệu để đánh giá ảnh hưởng đến api đang sử dụng | dev phụ trách | 2 lần/ tháng, 30 phút kiển tra mỗi lần  |
| 3 | pain từ người khác | dev backend sửa/thêm/xoá api nhưng không cập nhật tài liệu dẫn đến dev frontend phụ trách phỉa hỏi lại | dev phụ trách api | 5 lần/ tuần, 10 phút mỗi lần |
| 4 | lặp lại | sau khi sửa chức năng , phải tự thao tác thủ công từng bước để kiểm tra lại | dev và tester | 5 lần/ tuần, 30 phút mỗi lần |
| 5 | tốn thời gian | dev frontend phải thử nhiều kích thước màn hình để sửa responsive khi vỡ bố cục | dev frontend | 5 lần/ tuần, 20 phút đánh giá và sửa mỗi lần |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi:
- Ý dùng được:
- Ý bỏ vì không phải pain thật:

**Self-check Phase 1:**
- [ ] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể
- [ ] Dùng ít nhất 3/4 lăng kính
- [ ] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| 1 | dev backend sửa/thêm/xoá api nhưng không cập nhật tài liệu dẫn đến dev frontend phụ trách phải hỏi lại | phải trao đổi lại khi không cần thiết, mất thời gian làm việc khác |  |
| 2 | dev frontend phải thử nhiều kích thước màn hình để sửa responsive khi vỡ bố cục hoặc tạo giao diện mới | tốn thời gian, sửa lâu, phải thử nhiều kích thước màn | |
| 3 | sau khi sửa chức năng , phải tự thao tác thủ công từng bước để kiểm tra lại | công việc lặp lại gây nhàm chán | |

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

> cách đọc: số liệu hiện trạng lấy từ Phase 1; thời gian chia từng bước và mục tiêu cải thiện là giả định, cần đo lại khi kiểm chứng. workflow được vẽ trực tiếp bên dưới.

---

#### Problem Card #1 — backend thay đổi api nhưng không cập nhật tài liệu

```text
Problem 1 câu: dev backend sửa/thêm/xoá api nhưng không cập nhật tài liệu dẫn đến dev frontend phụ trách phải hỏi lại

Actor: dev frontend tích hợp api, dev backend phụ trách api

Thời điểm / bối cảnh: khi dev frontend tích hợp/ sửa chức năng sau khi backend cập nhật api

Current workflow 3-7 bước:
1. dev frontend gọi api thì phát hiện khác so với tài liệu
2. hỏi backend và trao đổi để xác nhận
3. ghi nhận thông tin và tiếp tục tích hợp api
4. dev backend cập nhật tài liệu

Bottleneck: bước 2 vì phải trao đổi lại với backend

Impact: 5 lần/ tuần, 10 phút mỗi lần, tổng 50 phút mỗi tuần chỉ để làm rõ api, làm chậm quá trình tích hợp/ cập nhật

Success metric: giảm số lần phải hỏi lại còn 0 - 1 lần/ tuần, mỗi lần trao đổi còn tối đa 4 phút, theo dõi trong 2 tuần

Non-AI alternative: dùng openapi làm api contract, bắt buộc cập nhật schema khi thay đổi api và kiểm tra trước khi merge

AI hypothesis: ai đọc thay đổi code và đề xuất cập nhật tài liệu, backend kiểm tra lại trước khi dùng

Quick gut:
[x] No AI / process fix
[ ] Rule
[ ] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #1** (ASCII / Mermaid / ảnh đính kèm):

```text
CURRENT STATE — 10 phút làm rõ api, chưa tính sửa code và cập nhật tài liệu

[phát hiện khác tài liệu: 2']
→ [hỏi backend để xác nhận: 6'] <-- bottleneck
→ [ghi nhận thông tin để tích hợp: 2']

FUTURE STATE — mục tiêu 4 phút làm rõ api

[đọc schema/ tài liệu đã cập nhật: 1']
→ [gọi thử api: 2']
→ [dev kiểm tra kết quả: 1'] <-- human boundary

backend cần cập nhật và kiểm tra tài liệu trước khi bàn giao api.

Fallback: nếu tài liệu vẫn sai thì hỏi backend xác nhận và cập nhật lại.
```

---

#### Problem Card #2 — mất thời gian thử và sửa responsive

```text
Problem 1 câu: dev frontend phải thử nhiều kích thước màn hình để sửa responsive khi vỡ bố cục hoặc tạo giao diện mới

Actor: dev frontend phụ trách giao diện

Thời điểm / bối cảnh: khi tạo giao diện mới hoặc sửa component làm ảnh hưởng bố cục

Current workflow 3-7 bước:
1. mở giao diện cần kiểm tra
2. thử nhiều kích thước màn hình để tìm chỗ vỡ bố cục
3. kiểm tra code và xác định nguyên nhân
4. sửa responsive
5. thử lại các kích thước để đảm bảo không lỗi chỗ khác

Bottleneck: bước 2 vì phải đổi kích thước và kiểm tra từng chỗ bằng mắt

Impact: 5 lần/ tuần, 20 phút mỗi lần, tổng 100 phút mỗi tuần để đánh giá và sửa responsive

Success metric: giảm từ 20 còn 12 phút mỗi lần, số lỗi responsive sau bàn giao không tăng, theo dõi trong 2 tuần trên cùng bộ kích thước kiểm tra

Non-AI alternative: tạo sẵn bộ kích thước cần kiểm tra, tự động chụp ảnh giao diện và so sánh trước/ sau

AI hypothesis: ai đọc ảnh giao diện và code để chỉ ra chỗ tràn/ lệch bố cục, gợi ý cách sửa, dev kiểm tra lại

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #2:**

```text
CURRENT STATE — 20 phút

[mở giao diện: 2']
→ [thử kích thước, tìm lỗi: 7'] <-- bottleneck
→ [tìm nguyên nhân: 4']
→ [sửa responsive: 4']
→ [kiểm tra lại: 3']

FUTURE STATE — mục tiêu 12 phút

[tự động chụp ảnh theo bộ kích thước: 2']
→ [dev xem ảnh, xác định lỗi: 3']
→ [sửa responsive: 4']
→ [chạy lại và dev kiểm tra: 3'] <-- human boundary

Fallback: nếu công cụ/ ai bỏ sót hoặc báo sai thì dev kiểm tra
thủ công ở kích thước gây lỗi và trên thiết bị thật.
```

---

#### Problem Card #3 — kiểm tra thủ công lặp lại sau khi sửa chức năng

```text
Problem 1 câu: sau khi sửa chức năng, dev và tester phải tự thao tác thủ công từng bước để kiểm tra lại

Actor: dev phụ trách chức năng, tester

Thời điểm / bối cảnh: sau khi sửa lỗi/ cập nhật chức năng, trước khi merge hoặc bàn giao

Current workflow 3-7 bước:
1. xác định các trường hợp cần kiểm tra
2. chuẩn bị tài khoản và dữ liệu test
3. thao tác thủ công từng trường hợp
4. kiểm tra kết quả có đúng mong đợi không
5. ghi nhận kết quả, báo lại nếu còn lỗi

Bottleneck: bước 3 vì phải lặp lại các thao tác sau mỗi lần sửa

Impact: 5 lần/ tuần, 30 phút mỗi lần, tổng 150 phút mỗi tuần, công việc lặp lại gây nhàm chán và dễ bỏ sót bước

Success metric: giảm từ 30 còn 15 phút mỗi lần với cùng bộ test, chạy đủ các trường hợp quan trọng và số lỗi lọt qua không tăng, theo dõi trong 2 tuần

Non-AI alternative: viết test tự động cho các luồng ổn định, dùng dữ liệu test có sẵn và chạy trong ci

AI hypothesis: ai đọc code thay đổi để gợi ý trường hợp cần test và viết nháp test, dev/ tester kiểm tra lại trước khi dùng

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #3:**

```text
CURRENT STATE — 30 phút

[chọn trường hợp cần test: 3']
→ [chuẩn bị dữ liệu: 4']
→ [thao tác thủ công: 15'] <-- bottleneck
→ [kiểm tra kết quả: 5']
→ [ghi nhận: 3']

FUTURE STATE — mục tiêu 15 phút khi đã có bộ test tự động

[chọn bộ test, chuẩn bị dữ liệu: 3']
→ [chạy test tự động: 5']
→ [dev/ tester xem kết quả và test phần còn lại: 5'] <-- human boundary
→ [ghi nhận: 2']

thời gian viết và bảo trì test cần theo dõi riêng.

Fallback: nếu test tự động lỗi hoặc chưa đủ trường hợp thì
dev/ tester kiểm tra thủ công theo checklist trước khi merge.
```

---

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```text
card #1 - backend thay đổi api nhưng không cập nhật tài liệu
```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text
khi tích hợp api, dev frontend phát hiện khác tài liệu thì phải hỏi backend rồi mới tiếp tục làm được.
theo số liệu ở Phase 1, việc này xảy ra 5 lần/ tuần, 10 phút mỗi lần, tổng 50 phút mỗi tuần chỉ để làm rõ api và còn làm gián đoạn backend.
chọn bài này vì điểm nghẽn rõ ở bước hỏi lại, có thể thử bắt buộc cập nhật schema trước khi merge rồi đo xem số lần hỏi và thời gian làm rõ có giảm không.
```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
nếu bắt buộc cập nhật openapi và kiểm tra trước khi merge đã giảm được số lần hỏi lại thì có cần ai không?
làm sao đảm bảo thời gian tiết kiệm cho frontend không chuyển thành nhiều thời gian cập nhật/ kiểm tra tài liệu hơn cho backend?
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: số liệu chưa được kiểm chứng; 50 phút mới tính phía frontend, chưa tính công cập nhật tài liệu của backend; mục tiêu 0 - 1 lần hỏi lại/ tuần cần thử mới biết có đạt không.
- Tôi sửa gì: bổ sung câu hỏi về tổng thời gian của cả frontend và backend, ưu tiên thử quy trình cập nhật schema trước, chưa chốt cần ai.

### Self-check nộp phần 01
- [ ] Có 5+ problems + top 3 Cards đủ field
- [ ] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [x] Đã chọn 1 card pitch + câu hỏi challenge
