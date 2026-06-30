# Báo cáo Lab Day 24: Phân tích Rủi ro AI - Ngành Y tế

## 1. Industry Risk Snapshot (Ngành Y tế)

*Đánh giá tổng quan ban đầu về mức độ rủi ro trước khi đi sâu vào phân tích các case study cụ thể.*

| Câu hỏi | Đánh giá (Low / Medium / High / Critical) | Vì sao? |
| :--- | :--- | :--- |
| **Nếu AI sai, có thể gây hại thể chất không?** | **Critical** | Chẩn đoán sai hoặc đưa ra lời khuyên y tế lệch lạc có thể trực tiếp dẫn đến thương vong, tổn hại sức khỏe vĩnh viễn hoặc tử vong. |
| **AI có ảnh hưởng đến quyết định hệ trọng không?** | **Critical** | Các quyết định như kê đơn thuốc, phẫu thuật, hay phác đồ điều trị ung thư đều là những quyết định mang tính sinh tử. |
| **Hệ thống có động tới dữ liệu nhạy cảm không?** | **Critical** | Dữ liệu sức khỏe, bệnh án cá nhân và thông tin sinh trắc học là những nhóm dữ liệu nhạy cảm cao nhất và được bảo vệ nghiêm ngặt về mặt pháp lý. |
| **Nếu sai, hậu quả có khó đảo ngược không?** | **Critical** | Bệnh nhân uống sai thuốc độc hại hoặc trễ thời gian vàng điều trị cấp cứu là những hậu quả tổn thương thể chất không thể đảo ngược. |
| **Nếu triển khai rộng, blast radius có lớn không?** | **High** | Nếu một ứng dụng Symptom Checker phổ biến bị lỗi cập nhật thuật toán, hàng triệu người dùng trên toàn thế giới có thể nhận chẩn đoán sai cùng một lúc. |
| **Có cần human review hoặc escalation không?** | **Critical** | Luôn luôn cần có bác sĩ hoặc chuyên gia y tế kiểm duyệt chéo (Human-in-the-loop) để chặn các sai sót nguy hiểm của AI. |
| **Risk profile tổng thể của ngành** | **Critical** | Y tế là ngành có mức độ rủi ro cao nhất vì tác động trực tiếp đến mạng sống và quyền con người. |

---

## 2. Danh sách Brief Cases thực tế

### 📑 Case Study 1: Epic Systems Sepsis Model Failure
* **Tên case:** Epic Systems Sepsis Model Failure
* **Ngành:** Y tế
* **Tổ chức / sản phẩm:** Hệ thống hồ sơ sức khỏe điện tử Epic Systems (Epic Sepsis Model)
* **Use case AI:** Thuật toán AI quét dữ liệu bệnh nhân để đưa ra cảnh báo sớm cho bác sĩ về nguy cơ nhiễm trùng huyết (sepsis).
* **Thời điểm:** Năm 2021.
* **Case xảy ra chuyện gì?:** Một nghiên cứu độc lập từ Đại học Michigan phát hiện mô hình AI dự báo nhiễm trùng huyết của Epic hoạt động kém hơn nhiều so với công bố của nhà sản xuất. Hệ thống bỏ sót phần lớn các ca nhiễm trùng nhiễm khuẩn và liên tục đưa ra hàng loạt cảnh báo sai gây nhiễu.
* **Stakeholder bị ảnh hưởng:** Bệnh nhân nội trú tại các bệnh viện, bác sĩ và điều dưỡng trực.
* **Số liệu chính:** Nghiên cứu trên **27.751 bệnh nhân** cho thấy AI đã **bỏ sót 67% số ca nhiễm trùng huyết** (tỉ lệ false negative nghiêm trọng) và tạo ra cảnh báo sai cho **18% số bệnh nhân không bị bệnh**, gây ra tình trạng "lờ cảnh báo" (alert fatigue) cho các y bác sĩ.
* **Trích nguồn ngắn & Link nguồn:** Nghiên cứu được xuất bản trên tạp chí y khoa danh tiếng JAMA Internal Medicine (2021). *Nguồn: Wong et al., "External Validation of a Widely Implemented Proprietary Sepsis Prediction Model", JAMA Intern Med, 2021*.
* **Ghi chú độ tin cậy:** Primary source (Nghiên cứu học thuật được peer-review kiểm chứng độc lập trên dữ liệu lâm sàng thực tế).

### 📑 Case Study 2: NEDA Tessa Chatbot Incident
* **Tên case:** NEDA Tessa Chatbot Incident
* **Ngành:** Y tế / Health assistant
* **Tổ chức / sản phẩm:** Hiệp hội Rối loạn Ăn uống Quốc gia Mỹ (NEDA) / Chatbot Tessa
* **Use case AI:** Chatbot AI được triển khai để thay thế đường dây nóng con người, nhằm lắng nghe và tư vấn tâm lý, hỗ trợ những người đang chống chọi với chứng rối loạn ăn uống.
* **Thời điểm:** Tháng 5 năm 2023.
* **Case xảy ra chuyện gì?:** Thay vì đưa ra các lời khuyên xoa dịu tâm lý, Tessa đột ngột đưa ra các hướng dẫn giảm cân, đếm calo nguy hiểm và cực đoan, hoàn toàn đi ngược lại các phác đồ y khoa cho người bị rối loạn ăn uống. Tổ chức NEDA đã phải gỡ bỏ chatbot này ngay lập tức.
* **Stakeholder bị ảnh hưởng:** Người dùng ứng dụng, những bệnh nhân đang có tâm lý bất ổn hoặc mắc chứng chán ăn, cuồng ăn.
* **Số liệu chính:** Chatbot đã hoạt động thay thế cho hotline vốn tiếp nhận hơn **70.000 cuộc gọi** mỗi năm; các chuyên gia phát hiện chatbot khuyên người bệnh cắt giảm **500 - 1.000 calo** mỗi ngày, một lời khuyên có thể kích hoạt hành vi tự hại lâm sàng.
* **Trích nguồn ngắn & Link nguồn:** Vụ việc được phản ánh trực tiếp bởi các nhà hoạt động và sau đó được tổ chức NEDA xác nhận, gỡ bỏ hệ thống vào cuối tháng 5/2023. *Nguồn: NPR News, "An eating disorders chatbot was taken down after giving advice on weight loss", 2023*.
* **Ghi chú độ tin cậy:** Secondary source chất lượng cao (Báo chí điều tra uy tín dẫn thông cáo chính thức của tổ chức điều hành).

---

## 3. Harm Map Worksheets

### 📊 Worksheet cho Case 1: Epic Sepsis Model

| Yếu tố phân tích | Label / Nội dung phân tích | Vì sao? |
| :--- | :--- | :--- |
| **High-risk moment** | Khi AI chạy ngầm quét dữ liệu lâm sàng của bệnh nhân đang trong cơn nguy kịch. | Thời điểm này quyết định bác sĩ có vào cuộc can thiệp kịp thời hay không. |
| **Stakeholder bị ảnh hưởng** | Bệnh nhân cấp cứu/nội trú và đội ngũ y tế trực lâm sàng. | Tính mạng bệnh nhân bị đe dọa; bác sĩ chịu áp lực tâm lý và quá tải thông tin. |
| **Failure mode** | Over-reliance (Quá tin tưởng) & Hallucination (Sai số thuật toán) | Hệ thống nhận diện sai lệch dữ liệu thực tế và y bác sĩ có thể mất cảnh giác vì ỷ lại vào máy. |
| **Layer bắt đầu lỗi** | Model | Lỗi nằm ở bản chất thuật toán dự báo cốt lõi của nhà sản xuất cấu hình sai. |
| **Harm xảy ra là gì?** | Can thiệp y tế bị trì hoãn dẫn đến bệnh diễn tiến nặng, có nguy cơ tử vong do sốc nhiễm khuẩn. | AI bỏ sót tới 67% số ca bệnh khiến việc điều trị kháng sinh bị chậm trễ. |
| **Harm lens** | Injury | Tổn hại thể chất nghiêm trọng, đe dọa trực tiếp mạng sống. |
| **Severity** | Critical | Có thể gây tử vong hoặc tổn thương cơ thể không thể phục hồi. |
| **Scale** | High | Hệ thống được áp dụng tại hàng trăm bệnh viện lớn, ảnh hưởng đến hàng chục nghìn bệnh nhân. |
| **Probability** | High | Mô hình hoạt động liên tục trên mọi bệnh nhân, tỉ lệ bỏ sót thực tế đã được chứng minh là rất cao. |
| **Frequency** | High | Lỗi xảy ra lặp đi lặp lại hàng ngày dưới dạng các cảnh báo sai liên tục tạo ra alert fatigue. |

### 📊 Worksheet cho Case 2: Chatbot Tessa

| Yếu tố phân tích | Label / Nội dung phân tích | Vì sao? |
| :--- | :--- | :--- |
| **High-risk moment** | Khi người bệnh đang trong trạng thái tâm lý khủng hoảng nhắn tin tìm kiếm lời khuyên từ chatbot. | Đây là lúc tâm lý họ dễ bị tổn thương và dễ nghe theo chỉ dẫn nhất. |
| **Stakeholder bị ảnh hưởng** | Bệnh nhân mắc hội chứng rối loạn ăn uống. | Họ trực tiếp làm theo lời khuyên và tự hủy hoại sức khỏe cơ thể. |
| **Failure mode** | Harmful advice (Lời khuyên độc hại) & Hallucination | AI tự tạo ra các thông tin, chỉ dẫn giảm cân cực đoan gây nguy hiểm. |
| **Layer bắt đầu lỗi** | Safety hoặc Grounding | Hệ thống thiếu các bộ lọc kiểm soát an toàn (Guardrails) để chặn các phản hồi độc hại về y tế. |
| **Harm xảy ra là gì?** | Bệnh nhân làm theo lời khuyên nhịn ăn/cắt giảm calo làm trầm trọng hóa bệnh lý rối loạn tâm thần/ăn uống. | Khiến thể trạng suy kiệt trầm trọng. |
| **Harm lens** | Injury & Dignity loss | Vừa tổn hại sức khỏe thể chất, vừa gây khủng hoảng tinh thần, ảnh hưởng phẩm giá người bệnh. |
| **Severity** | High đến Critical | Đẩy người bệnh vào trạng thái suy dinh dưỡng cấp tính hoặc hành vi tự hại. |
| **Scale** | Medium | Ảnh hưởng trực tiếp đến nhóm người dùng sử dụng hotline hỗ trợ của NEDA. |
| **Probability** | Medium | Xuất hiện khi người dùng kích hoạt các từ khóa liên quan đến cân nặng mà hệ thống không có rào chắn chặn lại. |
| **Frequency** | Medium | Xảy ra liên tục trong các phiên trò chuyện cho đến khi bị phát hiện và gỡ bỏ hoàn toàn. |

---

## 4. Tổng hợp Pattern Rủi ro của Ngành (Cá nhân)

> **Pattern rủi ro ngành Y tế:** Qua các case study thực tế, pattern rủi ro lớn nhất của AI trong ngành y tế là sự kết hợp giữa lỗi **Hallucination/Harmful advice** từ phía công nghệ và tâm lý **Over-reliance** từ phía con người (cả y bác sĩ lẫn bệnh nhân). Do đặc thù dữ liệu y tế phức tạp, các sai lệch thường bắt nguồn từ tầng **Model** (thuật toán dự báo thiếu chính xác) hoặc tầng **Safety** (thiếu hàng rào bảo vệ phản hồi). Hệ quả của những sai sót này không đơn thuần là sự phiền toái, mà có xu hướng hội tụ trực tiếp về harm lens **Injury** với mức độ **Severity ở ngưỡng Critical** – đe dọa trực tiếp đến tính mạng con người và rất khó để đảo ngược hậu quả một khi tổn thương thể chất đã xảy ra.

## 5. Bảng so sánh các ngành — Kết quả thảo luận cùng cả bàn (Nhóm)

| Ngành | Harm dễ gặp nhất | Failure mode hay lặp lại | Layer hay bắt đầu lỗi | Risk profile tổng thể | Vì sao? |
| :--- | :--- | :--- | :--- | :---: | :--- |
| **Mobility / Autonomous Driving** | Va chạm, thương tích, tử vong | Escalation failure, over-reliance, distribution shift | Safety + UX + Governance | **Critical** | Quyết định AI tác động tức thời đến hệ thống phanh, lái xe trong môi trường vật lý thời gian thực, có rủi ro tai nạn trực tiếp. |
| **Y tế / Medical AI** | Trì hoãn điều trị, phác đồ sai nguy hiểm, tự hại/tổn hại thể chất | Over-reliance, Hallucination, Harmful advice, Bias/Fairness | Model + Grounding + Safety + UX | **Critical** | Mô hình dự báo sai hoặc khuyên dùng thuốc gây biến chứng nặng nguy hiểm đến tính mạng bệnh nhân và khó đảo ngược. |
| *HR / Tuyển dụng (Điền thêm sau thảo luận)* | | | | | |
| *Giáo dục / AI Tutor (Điền thêm sau thảo luận)* | | | | | |

### 💬 Kết quả trả lời các câu hỏi thảo luận chung (Bước 6):
* **Ngành nào có Severity tiềm năng cao nhất?** -> **Y tế** và **Mobility** (do chạm đến tính mạng con người, harm vật lý là Injury).
* **Ngành nào có Scale tiềm năng lớn nhất?** -> Ngành **Media / News / Social** và **Content Creator** (AI lan truyền thông tin sai lệch - Misinformation có thể tiếp cận hàng triệu người chỉ trong vài giây).
* **Ngành nào có Probability hoặc Frequency cao nhất?** -> Ngành **Content Creator** và **Giáo dục / AI Tutor** (AI liên tục tạo nội dung mới hàng ngày, tần suất gặp Hallucination cực kỳ phổ biến).
* **Ngành nào xử lý dữ liệu nhạy cảm rõ nhất?** -> **Y tế** (Thông tin bệnh án, sinh trắc học cá nhân) và **HR/Tuyển dụng** (Thông tin lương thưởng, background kiểm tra lý lịch).
* **Ngành nào cần Human-in-the-loop (con người kiểm duyệt chéo) rõ nhất?** -> **Y tế** (Cần bác sĩ duyệt phác đồ trước khi áp dụng) và **Mobility** (Tài xế luôn phải sẵn sàng cầm lái khi hệ thống tự lái báo Escalation).
* **Ngành nào cần nâng rào cản (bar) để "được ship" sản phẩm cao nhất?** -> **Y tế** và **Mobility** (Phải trải qua các khâu kiểm duyệt gắt gao của các cơ quan quản lý nhà nước như FDA, Bộ GTVT trước khi thương mại hóa).

### 📝 Tổng hợp ngắn về risk profile giữa các ngành:
Cả hai ngành Mobility và Y tế đều thuộc nhóm có risk profile **Critical** do đều có khả năng gây ra thiệt hại vật lý không thể đảo ngược (*Injury / Death*) khi AI gặp lỗi.

* **Giống nhau:** Đều đối mặt với rủi ro lớn từ xu hướng *Over-reliance* của con người (ỷ lại hoàn toàn vào AI dự báo nhiễm trùng huyết, phác đồ điều trị ung thư hoặc phó mặc hoàn toàn cho hệ thống tự lái Level 2 khi tham gia giao thông).
* **Khác biệt về phân lớp lỗi bắt đầu (Layer):** * Lỗi của ngành tự hành (Mobility) thường bắt đầu mạnh từ tầng **Safety + UX + Governance** (liên quan đến vận hành thực tế ngoài đường công công, năng lực ứng biến khẩn cấp của người lái và thiết kế giao diện cảnh báo trực quan HMI).
  * Lỗi của ngành Y tế trải rộng từ tầng **Model** (như mô hình Epic Sepsis bỏ sót ca bệnh do cấu hình toán học), tầng **Grounding** (như IBM Watson Oncology huấn luyện trên dữ liệu giả lập thay vì bệnh án thực tế dẫn đến gợi ý phác đồ sai lệch), cho tới tầng **Safety & UX** (chatbot Tessa thiếu bộ lọc kiểm soát - Guardrails để chặn các lời khuyên ăn kiêng độc hại, đồng thời hệ thống cảnh báo dày đặc tạo ra hội chứng quá tải thông tin - alert fatigue cho y bác sĩ).