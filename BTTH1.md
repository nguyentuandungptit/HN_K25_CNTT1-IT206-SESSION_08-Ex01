# Bài thực hành 1: Ước lượng Product Backlog cho nền tảng bán hàng qua livestream

Môn học: [IT-206-K25] Quy trình phát triển phần mềm với Agile/Scrum  
Session 08: Thực hành Estimation & Sprint Planning  
Học viên thực hiện: Học viên Rikkei Academy  

---

## Nhiệm vụ 1: Kiểm tra dữ liệu trước khi ước lượng

| Mã Story | Đủ rõ | Cần làm rõ | Thông tin/câu hỏi còn thiếu |
| :--- | :---: | :---: | :--- |
| LS01 | ☐ | ☑ | Đến giờ phát, hệ thống có cần tự đổi trạng thái livestream không hay chỉ lưu dữ liệu và hiện "Sắp diễn ra"? (AC1 về tiêu đề đã rõ, nhưng AC2 mới chỉ nói đến trạng thái trước giờ phát; cần biết có phải tự động đổi trạng thái không để tính đúng phạm vi công việc). |
| LS03 | ☐ | ☑ | Khi nhiều khách cùng bấm mua những món cuối cùng, hệ thống xử lý tranh chấp giữ tồn kho (concurrency) thế nào và báo lỗi ra sao cho người mua hụt? (Story có 3 AC về nhập thông tin, cấp mã theo tồn kho và hoàn tồn, nên cần chốt rõ cơ chế khóa tồn kho để lường trước độ khó khi code). |

---

## Nhiệm vụ 2: Phân tích Planning Poker và chốt Story Point

### Bảng Product Backlog đã ước lượng

| Mã Story | Mức ưu tiên | Kết quả phiếu | SP chốt | Lý do ngắn gọn |
| :--- | :---: | :---: | :---: | :--- |
| LS01 | 1 | 3 - 3 - 5 - 3 | 3 | Dev C chấm 5 do tưởng phải xử lý tự đổi trạng thái theo giờ. Sau khi PO chốt story này chỉ cần hiện "Sắp diễn ra" (phần tự đổi trạng thái thuộc story khác), độ khó tương đương reference story LS02 nên chốt 3 SP. |
| LS02 | 2 | 3 - 3 - 3 - 3 | 3 | Story mốc (reference), cả nhóm đều đồng thuận 3 SP. |
| LS03 | 3 | 5 - 8 - 8 - 5 | 5 | Ban đầu nhóm chấm 8 lo ngại vấn đề tranh chấp khi mua đồng thời. Sau khi PO chốt quy tắc (ai bấm trước giữ hàng trước, hết hàng thì báo lỗi ngay), nhóm thống nhất chốt 5 SP. Độ khó cao hơn LS02 vì có thêm kiểm tra tồn kho và hoàn tồn khi hủy đơn. |

---

## Nhiệm vụ 3: Phản biện cách hiểu sai

Đề xuất của thành viên: *"Để dễ lập lịch, nhóm cố định 1 Story Point = 4 giờ cho mọi User Story."*

Giải thích phản biện:

Quy đổi cố định 1 Story Point = 4 giờ là sai bản chất của Scrum. Story Point dùng để ước lượng tương đối dựa trên độ khó, khối lượng công việc và rủi ro kỹ thuật so với một story chuẩn (như LS02 là 3 SP), chứ không phải thước đo thời gian tuyệt đối. 

Cùng một story 3 SP, lập trình viên có kinh nghiệm có thể làm xong trong nửa ngày, còn người mới có thể mất cả ngày. Để dự báo khối lượng công việc có thể nhận cho Sprint tới, đội Scrum dựa vào Velocity (tổng point trung bình hoàn thành ở các Sprint trước) thay vì quy đổi point sang giờ.
