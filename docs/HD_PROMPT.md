# KỸ THUẬT VIẾT PROMPT


* TOC
{:toc}
---

## 1. Prompt là gì?
Prompt là một đoạn văn bản hoặc câu lệnh được sử dụng để hướng dẫn hoặc kích hoạt một mô hình ngôn ngữ lớn (LLM). Prompt có thể bao gồm câu hỏi, yêu cầu, hoặc bất kỳ thông tin nào mà người dùng muốn mô hình phản hồi hoặc thực hiện.

## 2. Công thức viết Prompt hiệu quả
Một prompt hiệu quả thường tuân theo các nguyên tắc sau:
1. Nhập vai: Cho mô hình biết vai trò của nó và phong cách trả lời mong muốn. Ví dụ: "Bạn là một chuyên gia về lịch sử, hãy trả lời câu hỏi sau..."
2. Giao nhiệm vụ: Cung cấp nhiệm vụ cụ thể mà bạn muốn mô hình thực hiện. Nhiệm vụ càng rõ ràng thì đầu ra càng cụ thể, sát với yêu cầu.
3. Đưa ra yêu cầu chi tiết: AI sẽ tự điền vào chỗ trống nếu thiếu thông tin, nên cần thêm bối cảnh, yêu cầu định dạng, độ dài, ví dụ mẫu...
4. Chỉ dẫn và tinh chỉnh: Chỉ dẫn cách thức trả lời, định dạng đầu ra, ngôn ngữ sử dụng, phong cách viết... để phù hợp với mục đích sử dụng. Tiếp tục tinh chỉnh khi trả lời chưa đúng ý.

## 3. Ví dụ về Prompt hiệu quả
> Soạn kế hoạch công việc chi tiết cho `Mục tiêu công việc`. Kế hoạch cần bao gồm `Các giai đoạn/phần chính`. Thời gian thực hiện dự kiến `Ngày bắt đầu` đến `Ngày kết thúc`. 
> Mục tiêu cụ thể của kế hoạch này là: `Liệt kê mục tiêu`. Các nhiệm vụ/hoạt động chính cần thực hiện: `Nhiệm vụ/hoạt động chính` `Mô tả ngắn gọn`
> Các nguồn lực cần thiết (nhân sự, tài chính, công cụ,...). Các rủi ro tiềm ẩn và phương án ứng phó, giảm thiểu. Tiêu chí đánh giá thành công của kế hoạch.
> Định dạng đầu ra mong muốn. `Bảng/danh sách/văn bản trình bày`. Giọng điệu: `Chuyên nghiệp, thân thiện, trang trọng,...`. Độ dài: `Số từ/số trang`. Ngôn ngữ: `Tiếng Việt/Tiếng Anh/...`.