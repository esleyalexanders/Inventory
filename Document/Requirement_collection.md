

### **Tài liệu Phân tích Yêu cầu Nghiệp vụ: Hệ thống Quản lý Sản xuất và Tồn kho (ERP Mini)**

**Ngày:** 13/10/2025
**Người phân tích:** Business Analyst

#### **1. Tổng quan (Overview)**

Doanh nghiệp hoạt động trong lĩnh vực sản xuất và gia công sản phẩm, với chu trình từ quản lý nguyên vật liệu, sản xuất tại xưởng, kết hợp gia công bên ngoài (outsource) đến xuất nhập khẩu và giao hàng cho khách.

Dự án này nhằm mục đích xây dựng một hệ thống thông tin tập trung để giải quyết các vấn đề tồn đọng trong việc quản lý tồn kho, lập kế hoạch sản xuất và theo dõi đơn hàng, từ đó tối ưu hóa hiệu suất hoạt động và đảm bảo cam kết với khách hàng.

#### **2. Bối cảnh và Vấn đề (Context & Problem Statement)**

Hiện tại, quy trình vận hành của công ty đang gặp phải nhiều thách thức do phụ thuộc vào các phương pháp thủ công và thiếu một hệ thống quản lý đồng bộ:

* **Thiếu chính xác trong quản lý tồn kho:** Việc kiểm soát số lượng nguyên vật liệu (component), bán thành phẩm và thành phẩm (BOM) không chính xác, dẫn đến tình trạng "hao hụt thông tin", không nắm được số lượng thực tế có sẵn để sản xuất (stock available).
* **Khó khăn trong lập kế hoạch sản xuất:** Khi nhận đơn hàng lớn (PO), việc tính toán khả năng đáp ứng rất khó khăn. Phải kiểm tra thủ công tồn kho BOM, nếu thiếu lại phải kiểm tra đến bán thành phẩm và nguyên vật liệu. Quá trình này mất thời gian và dễ sai sót.
* **Chậm trễ trong giao hàng (Trễ deadline):** Do không dự báo chính xác được ngày có đủ nguyên vật liệu (material available date) và thời gian sản xuất (bao gồm cả OT, năng lực sản xuất), công ty thường xuyên bị động trước các sự cố như nhà cung cấp giao hàng chậm.
* **Thiếu minh bạch khi làm việc với đối tác gia công (Outsource):** Việc quản lý số lượng bán thành phẩm gửi đi gia công, theo dõi tiến độ và tích hợp vào kế hoạch sản xuất chung còn phức tạp.
* **Không thể tối ưu hóa chi phí:** Việc tính toán chi phí sản xuất (nguyên vật liệu, nhân công) và giá bán chưa được hệ thống hóa, gây khó khăn trong việc quản lý lợi nhuận.
* **Thiếu cái nhìn tổng thể:** Ban lãnh đạo không có dashboard hay báo cáo trực quan để nắm bắt nhanh chóng tình hình sản xuất, kinh doanh, tồn kho.

#### **3. Mục tiêu của Hệ thống (System Objectives)**

Hệ thống được xây dựng nhằm đạt được các mục tiêu sau:

* **SO1:** Cung cấp thông tin tồn kho (nguyên vật liệu, bán thành phẩm, thành phẩm) chính xác và theo thời gian thực.
* **SO2:** Tự động hóa quy trình lập kế hoạch sản xuất, từ việc phân tích đơn hàng đến đề xuất kế hoạch sản xuất/mua hàng.
* **SO3:** Cung cấp khả năng dự báo chính xác ngày hoàn thành và giao hàng cho khách hàng.
* **SO4:** Quản lý hiệu quả các hoạt động gia công bên ngoài.
* **SO5:** Chuẩn hóa và quản lý tập trung toàn bộ dữ liệu gốc (Master Data) của hệ thống.
* **SO6:** Cung cấp các báo cáo và dashboard trực quan để hỗ trợ ra quyết định.

#### **4. Phân tích Yêu cầu Chức năng (Functional Requirements)**

Hệ thống sẽ được chia thành các module chính với các chức năng cụ thể như sau:

**Module 1: Quản lý Dữ liệu Gốc (Master Data Management)**

* **F1.1 - Quản lý Component (Component Master):**
    * Tạo và quản lý danh sách các nguyên vật liệu (nhựa, gỗ, sơn, thùng carton, etc.).
    * Thông tin chi tiết: Mã NVL, tên NVL, đơn vị tính (cái, m³, lít, ...), nhà cung cấp, lead time mua hàng, giới hạn số lượng nhập tối đa/lần.
* **F1.2 - Quản lý BOM (Bill of Materials Master):**
    * Tạo và quản lý công thức định mức cho một sản phẩm hoàn chỉnh (Thành phẩm).
    * Chi tiết: 1 Mã BOM sẽ bao gồm danh sách các Component cần thiết và số lượng tương ứng.
    * Quản lý thông tin về năng lực sản xuất của nhà máy đối với từng loại BOM (sản phẩm/ngày).
* **F1.3 - Quản lý Quy cách đóng gói (Packaging Master):**
    * Định nghĩa các quy cách đóng gói: số lượng thành phẩm/thùng.
    * Cho phép tùy chỉnh quy cách đóng gói theo yêu cầu riêng của từng đơn hàng/khách hàng (ví dụ: 1 thùng to hoặc N thùng nhỏ).

**Module 2: Quản lý Kho (Inventory Management)**

* **F2.1 - Quản lý Nhập/Xuất kho:**
    * Thực hiện các giao dịch nhập kho nguyên vật liệu, bán thành phẩm, thành phẩm.
    * Thực hiện xuất kho nguyên vật liệu cho sản xuất, xuất kho thành phẩm giao hàng.
    * Kiểm soát số lượng nhập hàng chặt chẽ.
* **F2.2 - Theo dõi Tồn kho:**
    * Hiển thị tồn kho của tất cả các mặt hàng (NVL, bán thành phẩm, thành phẩm).
    * Phân biệt rõ các trạng thái tồn kho:
        * **Tồn kho có sẵn (Stock Available):** Số lượng có thể sử dụng ngay.
        * **Tồn kho đang giữ/khóa (Stock on Hand/Locked):** Số lượng đã được cam kết cho một lệnh sản xuất cụ thể.
* **F2.3 - Cảnh báo Tồn kho:**
    * Hệ thống tự động cảnh báo khi tồn kho của một nguyên vật liệu xuống dưới mức tối thiểu.
    * Gợi ý mua hàng dựa trên nhu cầu sản xuất sắp tới.

**Module 3: Quản lý Bán hàng & Đơn hàng (Sales & Order Management)**

* **F3.1 - Quản lý Đơn hàng (Purchase Order - PO):**
    * Tạo và quản lý thông tin đơn hàng của khách: Số PO, thông tin khách hàng, ngày đặt, ngày yêu cầu giao hàng.
    * Liệt kê danh sách các BOM và số lượng khách đặt.
* **F3.2 - Phân tích Khả năng Đáp ứng Đơn hàng:**
    * Khi nhận PO mới, hệ thống tự động:
        1.  Kiểm tra tồn kho thành phẩm (BOM).
        2.  Nếu không đủ, tính toán số lượng BOM cần sản xuất.
        3.  Kiểm tra tồn kho bán thành phẩm và nguyên vật liệu cần thiết để sản xuất số BOM thiếu hụt.
        4.  Dựa trên tồn kho và lead time mua hàng, hệ thống **tính toán và đề xuất ngày sớm nhất có thể có đủ nguyên vật liệu (Material Available Date)**.
        5.  Dựa trên năng lực sản xuất, hệ thống **ước tính thời gian hoàn thành sản xuất và đề xuất ngày giao hàng khả thi**.

**Module 4: Lập kế hoạch & Quản lý Sản xuất (Production Planning & Management)**

* **F4.1 - Lên Kế hoạch Sản xuất:**
    * Hệ thống tự động đề xuất kế hoạch sản xuất dựa trên các đơn hàng đang chờ.
    * Kế hoạch bao gồm: Số lượng BOM cần sản xuất, số lượng bán thành phẩm cần gia công, số lượng nguyên vật liệu cần xuất kho.
* **F4.2 - Quản lý Lệnh sản xuất:**
    * Tạo các lệnh sản xuất tương ứng với kế hoạch.
    * Theo dõi trạng thái của đơn hàng/lệnh sản xuất: Mới tạo, Đang sản xuất, Hoàn thành, Đã xuất hàng.
* **F4.3 - Quản lý Gia công ngoài (Outsource):**
    * Tạo và quản lý các đơn hàng gia công gửi cho đối tác.
    * Theo dõi số lượng bán thành phẩm gửi đi và nhận về.
    * Tích hợp thông tin từ đối tác gia công vào kế hoạch sản xuất chung (vd: số lượng cố định hàng tháng: 100,000).

**Module 5: Quản lý Chi phí & Doanh thu (Cost & Revenue Management)**

* **F5.1 - Tính giá vốn hàng bán (COGS):**
    * Tự động tính toán chi phí nguyên vật liệu để sản xuất ra một thành phẩm dựa trên BOM master.
    * *Giai đoạn sau:* Tích hợp chi phí nhân công và các chi phí khác.
* **F5.2 - Quản lý Giá bán:**
    * Thiết lập giá bán cho từng loại BOM.
* **F5.3 - Theo dõi Doanh thu:**
    * Ghi nhận doanh thu khi đơn hàng được xuất đi và hoàn thành.

**Module 6: Báo cáo & Dashboard**

* **F6.1 - Dashboard Tổng quan:**
    * Hiển thị các chỉ số chính: Tổng số đơn hàng (mới, đang xử lý, hoàn thành), giá trị tồn kho, doanh thu trong kỳ, hiệu suất sản xuất.
* **F6.2 - Báo cáo chi tiết:**
    * Báo cáo tồn kho.
    * Báo cáo tình hình thực hiện đơn hàng.
    * Báo cáo tiến độ sản xuất.
    * Báo cáo chi phí và lợi nhuận theo đơn hàng.

#### **5. Lộ trình Phát triển Đề xuất (Proposed Roadmap)**

Dựa trên yêu cầu, dự án có thể được chia thành các giai đoạn:

* **Giai đoạn 1: Xây dựng Lõi Vận hành (Core Operations)**
    * Triển khai các Module: 1 (Master Data), 2 (Inventory), 3 (Sales), 4 (Production), 6 (Basic Reporting).
    * **Mục tiêu:** Giải quyết các vấn đề cấp bách nhất về quản lý tồn kho và lập kế hoạch sản xuất.
* **Giai đoạn 2: Tối ưu hóa Tài chính (Financial Optimization)**
    * Triển khai Module 5 (Cost & Revenue).
    * Tích hợp quản lý thuế VAT cho nguyên vật liệu đầu vào.
    * Nâng cao Module báo cáo với các phân tích tài chính.
* **Giai đoạn 3: Quản lý Nguồn lực (Resource Management)**
    * Phát triển module Quản lý nhân công (tính toán năng suất, OT, chi phí nhân công chi tiết).

---