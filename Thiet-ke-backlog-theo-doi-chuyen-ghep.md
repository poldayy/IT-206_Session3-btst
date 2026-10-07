# SÁNG TẠO: TỪ NỖI ĐAU KHÁCH HÀNG ĐẾN KIẾN TRÚC BACKLOG HOÀN CHỈNH

## Thiết kế Backlog cho tính năng theo dõi chuyến ghép

**Sản phẩm:** RikkeiGo  
**Nhu cầu khách hàng:** “Tôi không biết xe đang đón ai, bao giờ đến lượt mình và khi có vấn đề thì phải làm gì.”

## Phần 1 – Thiết kế cấu trúc Epic, Feature và User Story

### Epic: Theo dõi chuyến ghép minh bạch và chủ động

Mục tiêu của Epic là giúp khách biết trạng thái chuyến, biết thứ tự đón và có hướng xử lý khi chuyến bị chậm hoặc phát sinh vấn đề.

    EPIC: Theo dõi chuyến ghép minh bạch và chủ động
    |
    |-- FEATURE 1: Xem trạng thái và tiến trình chuyến theo thời gian thực
    |   |-- US1. Với vai trò là khách đã đặt chuyến ghép, tôi muốn xem vị trí hiện tại và trạng thái chuyến trên bản đồ, để biết xe đang ở đâu và chuyến đang diễn ra đến bước nào.
    |   |
    |   |-- US2. Với vai trò là khách trong chuyến ghép, tôi muốn xem danh sách thứ tự đón và điểm đón hiện tại, để biết khi nào gần đến lượt mình.
    |
    |-- FEATURE 2: Nhận cảnh báo và được hướng dẫn khi chuyến có vấn đề
        |-- US3. Với vai trò là khách trong chuyến ghép, tôi muốn nhận thông báo khi xe sắp đến điểm đón của mình, để chủ động chuẩn bị và không bỏ lỡ xe.
        |
        |-- US4. Với vai trò là khách trong chuyến ghép, tôi muốn xem hướng dẫn xử lý khi xe chậm, không tìm thấy điểm đón hoặc không liên lạc được với tài xế, để biết cần thực hiện hành động nào tiếp theo.

### Diễn giải giá trị của các User Story

- **US1** giải quyết câu hỏi “xe đang ở đâu” và tạo thông tin nền tảng cho các phần theo dõi khác.
- **US2** giải quyết câu hỏi “bao giờ đến lượt mình” bằng thứ tự đón rõ ràng.
- **US3** chuyển thông tin theo dõi thành hành động cụ thể, giúp khách chuẩn bị đúng lúc.
- **US4** giải quyết tình huống bất thường, giúp khách không bị bỏ mặc khi chuyến gặp vấn đề.

Mỗi User Story có một người dùng, một nhu cầu và một giá trị trực tiếp. Có thể kiểm thử từng story bằng kết quả mà khách nhìn thấy hoặc thực hiện được.

## Phần 2 – Sắp xếp Product Backlog theo giá trị và D.E.E.P

### Thứ tự ưu tiên

| Ưu tiên | User Story | Lý do ưu tiên |
|---:|---|---|
| 1 | **US1 – Xem vị trí và trạng thái chuyến** | Đây là thông tin cốt lõi để giảm sự không chắc chắn của khách. Các cảnh báo và hướng dẫn phía sau cũng cần trạng thái chuyến làm dữ liệu đầu vào. |
| 2 | **US2 – Xem thứ tự đón và điểm đón hiện tại** | Trả lời trực tiếp câu hỏi “bao giờ đến lượt mình”, giúp khách dự kiến thời gian chờ và theo dõi tiến trình đón. |
| 3 | **US3 – Nhận thông báo khi xe sắp đến** | Tạo giá trị tiện lợi và giảm nguy cơ khách bỏ lỡ xe sau khi hệ thống đã có dữ liệu vị trí, trạng thái và thứ tự đón. |
| 4 | **US4 – Hướng dẫn xử lý khi có vấn đề** | Có giá trị cao khi xảy ra sự cố, nhưng tần suất sử dụng thấp hơn luồng theo dõi bình thường. Có thể hoàn thiện sau khi các trạng thái và tình huống chính đã được xác định. |

### Story cần chi tiết nhất

**US1 cần được chi tiết nhất trước khi đưa vào Sprint.** Đây là story ưu tiên số 1 và có nhiều rủi ro hơn các story còn lại vì phụ thuộc vào dữ liệu vị trí từ đối tác bản đồ, quyền truy cập vị trí, tần suất cập nhật và cách hiển thị khi dữ liệu bị trễ.

Theo D.E.E.P:

- **Detailed appropriately:** US1 cần Acceptance Criteria rõ về trạng thái chuyến, thời điểm cập nhật, sai số hoặc tình trạng mất dữ liệu. US3 và US4 có thể được chi tiết thêm sau khi luồng trạng thái cơ bản đã rõ.
- **Emergent:** Backlog được phép bổ sung trường hợp như dữ liệu bản đồ chậm, xe ngoài vùng phủ hoặc tài xế tắt chia sẻ vị trí khi đội đã có thêm thông tin từ thử nghiệm.
- **Estimated:** US1 cần được ước lượng sau khi làm rõ tích hợp bản đồ và dữ liệu vị trí. Nếu chưa đủ thông tin, đội nên tách một story khảo sát hoặc Spike trước khi cam kết.
- **Prioritized:** US1 đứng đầu vì tạo nền tảng và giá trị lớn nhất cho mục tiêu giảm lo lắng của khách. Các story sau sử dụng hoặc mở rộng dữ liệu do US1 cung cấp.

Bốn story đều là các mục backlog có thể hiểu và ước lượng ở mức phù hợp. Khi một story được kéo vào Sprint, Product Owner và đội phát triển sẽ bổ sung Acceptance Criteria, dữ liệu kiểm thử và điều kiện hoàn thành đến mức đủ để thực hiện.

## Phần 3 – Xử lý tình huống và rủi ro tiến độ

### Tình huống 1: Đường thực tế trên Burndown Chart đi ngang 3 ngày

**Dấu hiệu nhận biết:** Đường thực tế giữ nguyên trong 3 ngày liên tiếp, trong khi thời gian Sprint vẫn trôi và đường lý tưởng tiếp tục đi xuống. Điều này cho thấy số công việc còn lại chưa giảm; trong bối cảnh đề bài, nguyên nhân là dữ liệu vị trí từ đối tác bản đồ chưa được bàn giao.

**Người xử lý chính:** Scrum Master điều phối việc gỡ trở ngại; Product Owner làm rõ mức độ cần thiết của dữ liệu và trao đổi với bên liên quan; đội phát triển đánh giá phương án kỹ thuật và ảnh hưởng đến Sprint Goal.

**Cách xử lý:**

1. Đưa trở ngại lên Daily Scrum và ghi nhận rõ người phụ trách, thời hạn phản hồi từ đối tác bản đồ.
2. Scrum Master chủ động liên hệ và thúc đẩy việc gỡ phụ thuộc; không che giấu việc công việc chưa giảm bằng cách điều chỉnh số liệu Burndown.
3. Product Owner cùng đội xem lại Sprint Goal và phạm vi đã cam kết. Nếu dữ liệu thật chưa thể bàn giao, đội có thể làm phần không phụ thuộc như giao diện, mô hình trạng thái, xử lý dữ liệu mẫu hoặc Spike tích hợp, miễn là tạo ra Increment đáp ứng Definition of Done.
4. Nếu trở ngại khiến Sprint Goal không còn khả thi, Product Owner và đội điều chỉnh phạm vi theo năng lực thực tế; đưa phần chưa làm xong trở lại Product Backlog để sắp xếp lại.

### Tình huống 2: Đức muốn đưa nguyên Epic vào một Sprint Backlog

**Người xử lý chính:** Product Owner chịu trách nhiệm về thứ tự và giá trị Product Backlog; Scrum Master hướng dẫn nguyên tắc Scrum; Developers quyết định lượng công việc có thể thực hiện dựa trên năng lực và Sprint Goal.

**Cách xử lý:**

- Không đưa nguyên Epic vào Sprint Backlog như một mục việc duy nhất. Epic còn quá lớn, chưa đủ cụ thể để ước lượng và kiểm tra trong một Sprint.
- Product Owner cùng đội phân rã Epic thành các Feature và User Story như US1–US4, sau đó làm rõ Acceptance Criteria, phụ thuộc và kích thước từng story.
- Chọn một Sprint Goal có phạm vi vừa sức, ưu tiên US1 và US2 hoặc tách nhỏ US1 nếu việc tích hợp bản đồ còn rủi ro.
- Chỉ đưa các story đã đủ rõ và phù hợp với năng lực Sprint vào Sprint Backlog. Các story còn lại vẫn ở Product Backlog, được giữ thứ tự ưu tiên và tiếp tục làm rõ dần.
- Trong Sprint, đội có thể đàm phán điều chỉnh phạm vi với Product Owner khi có trở ngại, nhưng không làm giảm chất lượng của Increment hoặc bỏ qua Definition of Done.

## Kết luận

Backlog được thiết kế từ nỗi đau cụ thể của khách: không biết xe đang ở đâu, khi nào đến lượt và phải làm gì lúc có sự cố. Thứ tự ưu tiên bắt đầu bằng thông tin vị trí và trạng thái, tiếp đến là thứ tự đón, cảnh báo và hướng dẫn xử lý. Cách đưa từng User Story đã đủ rõ vào Sprint giúp đội kiểm soát rủi ro dữ liệu bản đồ và tránh biến cả Epic thành một mục việc quá lớn.
