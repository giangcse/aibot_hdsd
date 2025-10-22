# TÀI LIỆU KỸ THUẬT

## Mục lục
* TOC
{:toc}
---

## I. Generative AI (Gen AI), Large Language Model (LLM) và Retrieval‑Augmented Generation (RAG) là gì? Mối liên hệ giữa RAG và Gen AI?

> VIAIBOT là tên sản phẩm chatbot sử dụng kỹ thuật RAG để cung cấp câu trả lời.

### 1. Generative AI (Gen AI)
- Định nghĩa: Gen AI là nhóm các hệ thống trí tuệ nhân tạo có khả năng tạo ra nội dung mới, chẳng hạn văn bản, hình ảnh, âm thanh, mã lập trình… 
- Ví dụ: mô hình tạo ảnh từ prompt (“Generate an image of…”), hoặc tạo văn bản trả lời câu hỏi.
- Vai trò: Là phạm trù lớn – tất cả các công cụ tạo nội dung đều có thể nằm dưới Gen AI, trong đó có văn bản, hình ảnh, audio…
- Lưu ý: Gen AI không chỉ là “chatbot văn bản” — nó rộng hơn. Nhưng khi chỉ nói về văn bản/ngôn ngữ thì thường là tới LLM.

### 2. Large Language Model (LLM)
- Định nghĩa: LLM là một loại mô hình học máy rất lớn (“large”) chuyên xử lý ngôn ngữ – hiểu và tạo ra văn bản. 
- Cách nó hoạt động: Được huấn luyện trên khối lượng lớn văn bản, học ra các mẫu ngôn ngữ, cách sử dụng từ/cụm từ, rồi dự đoán “tiếp theo” trong chuỗi từ. 
- LLM nằm trong Gen AI: tất cả LLM đều là Gen AI nhưng không phải mọi Gen AI đều là LLM (vì có thể là tạo ảnh, video) 
- Ví dụ: GPT‑4, LLaMA …
- Lưu ý: Dù mạnh, LLM chỉ “giả lập” hiểu ngôn ngữ – không thật sự “hiểu” như con người.

### 3. Retrieval‑Augmented Generation (RAG)
- Định nghĩa: RAG là kỹ thuật kết hợp giữa mô hình ngôn ngữ lớn (LLM) với việc truy xuất thông tin từ nguồn dữ liệu bên ngoài trước khi sinh câu trả lời. 
- Cụ thể: Khi người dùng đặt câu hỏi, RAG sẽ tìm trong kho dữ liệu (ví dụ tài liệu nội bộ, website, cơ sở dữ liệu) những thông tin có liên quan → đưa vào prompt cho LLM → LLM dùng thông tin đó + kiến thức đã có để sinh câu trả lời. 
- Vì sao cần: LLM độc lập có giới hạn – có thể biết không đầy đủ, có thể “hallucinate” (bịa thông tin). RAG giúp tăng độ chính xác, cập nhật, chuyên sâu. 
- Ví dụ ứng dụng: Chatbot doanh nghiệp sử dụng dữ liệu nội bộ để trả lời nhân viên thay vì chỉ dựa trên kiến thức mạng.

### 4. Mối liên hệ giữa Gen AI ↔ LLM ↔ RAG

![RAG-GenAI-LLM](images/ragdiagram.png)

- Gen AI là khung lớn nhất: nó nói về mọi hệ thống AI tạo nội dung.
- LLM là một thành phần đặc biệt của Gen AI, tập trung vào văn bản/ngôn ngữ.
- RAG là một kỹ thuật/kiến trúc dùng để nâng cao hiệu suất của LLM (và nằm trong Gen AI) — tức là RAG dùng LLM + truy xuất dữ liệu.

Tóm lại:
- Gen AI ↠ (bao gồm) ↠ LLM ↠ (có thể dùng) ↠ RAG
- Khi bạn xây chatbot: thường bạn sẽ sử dụng một LLM (ví dụ GPT) có thể kèm RAG để cải thiện kiến thức.

Ví dụ:
- Một hệ thống Gen AI tạo ảnh – không phải LLM.
- Một chatbot văn bản = LLM.
- Một chatbot văn bản dùng kho dữ liệu nội bộ để trả lời chính xác hơn = LLM + RAG.

### 5. Cách hoạt động của RAG
**Quy trình RAG gồm hai bước chính:**
1. Truy xuất (Retrieval):
    - Khi người dùng hỏi, chatbot không chỉ dựa vào kiến thức đã được huấn luyện.
    - Nó sẽ tìm kiếm (truy xuất) dữ liệu liên quan trong một knowledge base (VD: tài liệu nội bộ, database, vector store, hoặc web).
    - Thông thường, dữ liệu được lưu dưới dạng embedding và được tìm bằng tìm kiếm ngữ nghĩa (semantic search).

2. Tăng cường và Sinh (Augmentation & Generation):
    - Các đoạn văn bản đã tìm được sẽ được đưa vào prompt, làm ngữ cảnh bổ sung cho mô hình ngôn ngữ (LLM).
    - Mô hình LLM sau đó dùng thông tin này để tạo câu trả lời chính xác và cập nhật hơn.

**Ưu điểm**
- Cập nhật kiến thức động: Không bị giới hạn trong dữ liệu huấn luyện tĩnh của LLM.
- Chính xác hơn: Vì mô hình có thể trích dẫn từ nguồn gốc.
- Tiện cho doanh nghiệp: Dễ tích hợp với tài liệu nội bộ (FAQ, policy, wiki…).

**Nhược điểm**
- Phụ thuộc vào chất lượng dữ liệu và tìm kiếm ngữ nghĩa.
- Cần hệ thống hạ tầng lưu trữ & truy xuất (vector database: Pinecone, Weaviate, Milvus, FAISS...).
- Nếu truy xuất kém, câu trả lời dễ bị sai lệch.
