# 23655901_lehoangyen_cabsystem

# 1. Vấn đề danh nghiệp
- Đặt xe còn phụ thuộc nhiều vào tổng đài và thao tác thủ công.
- Việc tìm và phân công tài xế chưa tự động, khó mở rộng khi số lượng chuyến tăng.
- Khách hàng khó theo dõi trạng thái chuyến đi theo thời gian thực.
- Thông tin cước phí và thanh toán chưa được quản lý tập trung.
- Việc gửi thông báo chưa có kiến trúc linh hoạt để mở rộng nhiều kênh.
- Nhân viên vận hành thiếu công cụ để theo dõi, xử lý và quản lý chuyến.
- Khó kiểm soát quyền truy cập, bảo mật và lịch sử thao tác.
- Hệ thống chưa có khả năng mở rộng tốt khi nhu cầu tăng cao.
- Nhiều chính sách nghiệp vụ quan trọng vẫn chưa được xác định rõ.
# 2. Xác định stakeholder
| STT | Stakeholder | Vai trò  |
| --- | --- | --- |
| 1 | **Ban giám đốc** | Định hướng dự án, phê duyệt ngân sách, theo dõi hiệu quả kinh doanh và báo cáo tổng thể. |
| 2 | **Khách hàng** | Đăng ký, đặt xe, theo dõi chuyến, thanh toán, xem lịch sử và đánh giá tài xế. |
| 3 | **Tài xế** | Quản lý hồ sơ, phương tiện, trạng thái hoạt động; nhận và thực hiện chuyến; cập nhật trạng thái và vị trí. |
| 4 | **Nhân viên vận hành** | Quản lý khách hàng, tài xế, phương tiện, chuyến đi; giám sát và xử lý các trường hợp bất thường. |
| 5 | **Bộ phận IT / Kỹ thuật** | Phát triển, triển khai, vận hành, bảo trì, đảm bảo hiệu năng, khả năng mở rộng và tích hợp hệ thống. |
| 6 | **Bộ phận Tài chính / Kế toán** | Theo dõi doanh thu, giao dịch, đối soát thanh toán và hỗ trợ báo cáo tài chính. |
| 7 | **Bộ phận Quản trị / Bảo mật** | Quản lý quyền truy cập, bảo vệ dữ liệu, kiểm tra nhật ký thao tác và xử lý các vấn đề bảo mật. |
| 8 | **Nhà cung cấp thanh toán** | Xử lý các giao dịch thanh toán điện tử và trả kết quả giao dịch cho hệ thống CAB. |
| 9 | **Nhà cung cấp dịch vụ thông báo** | Cung cấp SMS, email, push notification và hỗ trợ mở rộng thêm các kênh thông báo. |

# Stakeholder Matrix

Ma trận Stakeholder được phân loại dựa trên hai tiêu chí:
- **Power:** Mức độ quyền lực/ảnh hưởng đến dự án.
- **Interest:** Mức độ quan tâm đến dự án.

```mermaid
quadrantChart
    title Stakeholder Matrix - CAB System
   x-axis Low Interest --> High Interest
    y-axis Low Power --> High Power

    quadrant-1 Manage Closely
    quadrant-2 Keep Satisfied
    quadrant-3 Monitor
    quadrant-4 Keep Informed

    "Ban giám đốc": [0.85, 0.90]
    "Nhân viên vận hành": [0.90, 0.80]
    "IT / Kỹ thuật": [0.85, 0.85]
    "Quản trị / Bảo mật": [0.80, 0.88]

    "Khách hàng": [0.90, 0.25]
    "Tài xế": [0.85, 0.20]
    "Tài chính / Kế toán": [0.70, 0.35]

    "Nhà cung cấp thanh toán": [0.35, 0.60]
    "Nhà cung cấp dịch vụ thông báo": [0.25, 0.20]
```
 # 3. Mục đích nghiệp vụ của các bên liên quan
## Mục đích của các Stakeholder
| STT | Stakeholder | Mục đích / Mối quan tâm |
| --- | --- | --- |
| 1 | **Ban giám đốc** | Nâng cao hiệu quả kinh doanh, kiểm soát hoạt động và có dữ liệu, báo cáo để hỗ trợ ra quyết định. |
| 2 | **Khách hàng** | Đặt xe thuận tiện, biết trạng thái chuyến, thông tin tài xế, thời gian dự kiến đến; thanh toán và đánh giá dịch vụ dễ dàng. |
| 3 | **Tài xế** | Nhận các chuyến phù hợp, quản lý trạng thái hoạt động, cập nhật vị trí và thực hiện chuyến thuận tiện. |
| 4 | **Nhân viên vận hành** | Quản lý, giám sát khách hàng, tài xế, phương tiện và chuyến đi; nhanh chóng phát hiện và xử lý các trường hợp bất thường. |
| 5 | **Bộ phận IT / Kỹ thuật** | Đảm bảo hệ thống hoạt động ổn định, bảo mật, có khả năng mở rộng và dễ dàng tích hợp hoặc thay đổi các thành phần kỹ thuật. |
| 6 | **Bộ phận Tài chính / Kế toán** | Theo dõi doanh thu, giao dịch, đối soát thanh toán và cung cấp dữ liệu phục vụ báo cáo tài chính. |
| 7 | **Bộ phận Quản trị / Bảo mật** | Kiểm soát quyền truy cập, bảo vệ dữ liệu và theo dõi các thao tác quan trọng để phục vụ kiểm tra, xử lý sự cố. |
| 8 | **Nhà cung cấp thanh toán** | Cung cấp dịch vụ thanh toán điện tử an toàn, ổn định và xử lý các giao dịch từ hệ thống CAB. |
| 9 | **Nhà cung cấp dịch vụ thông báo** | Cung cấp các kênh thông báo như SMS, email, push notification và hỗ trợ mở rộng thêm các kênh trong tương lai. |

## Business Goals – Mục tiêu nghiệp vụ

| ID | Business Goal | Ý nghĩa |
| --- | --- | --- |
| **BG01** | **Tự động hóa quy trình đặt và phân công xe** | Giảm sự phụ thuộc vào tổng đài và việc phân công tài xế thủ công. |
| **BG02** | **Nâng cao trải nghiệm khách hàng** | Giúp khách hàng dễ dàng đặt xe, theo dõi trạng thái chuyến, tài xế và thời gian dự kiến đến. |
| **BG03** | **Tối ưu hóa việc phân công tài xế** | Tự động tìm và ưu tiên tài xế phù hợp, gần khách hàng và đang sẵn sàng nhận chuyến. |
| **BG04** | **Quản lý tập trung hoạt động vận hành** | Cung cấp nền tảng quản lý khách hàng, tài xế, phương tiện và chuyến đi cho nhân viên vận hành. |
| **BG05** | **Nâng cao hiệu quả quản lý doanh thu và thanh toán** | Chuẩn hóa việc tính cước, quản lý giao dịch và hỗ trợ thanh toán tiền mặt, điện tử. |
| **BG06** | **Nâng cao khả năng giám sát và ra quyết định** | Cung cấp dữ liệu và báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, hủy chuyến và hiệu quả tài xế. |
| **BG07** | **Đảm bảo khả năng mở rộng của hệ thống** | Cho phép hệ thống phục vụ số lượng lớn khách hàng, tài xế và mở rộng các thành phần khi tải tăng. |
| **BG08** | **Tăng tính linh hoạt trong phát triển sản phẩm** | Cho phép bổ sung dịch vụ, phương thức thanh toán, kênh thông báo hoặc thay đổi thành phần kỹ thuật. |
| **BG09** | **Đảm bảo bảo mật và kiểm soát truy cập** | Bảo vệ thông tin cá nhân, phương tiện, vị trí, giao dịch và kiểm soát các thao tác quản trị. |
| **BG10** | **Nâng cao độ tin cậy và tính sẵn sàng** | Hạn chế ảnh hưởng dây chuyền khi một thành phần như thanh toán hoặc thông báo gặp lỗi. |
# 4. Phạm vi cơ bản của hệ thống
| STT | Module | Phạm vi cốt lõi |
|:---:|---|---|
| 1 | **Quản lý tài khoản & hồ sơ** | Đăng ký, đăng nhập, cập nhật thông tin khách hàng/tài xế; quản lý hồ sơ và phương tiện của tài xế. |
| 2 | **Đặt xe** | Khách hàng nhập điểm đón, điểm đến, chọn loại xe. |
| 3 | **Tìm tài xế** | Hệ thống tìm và phân công tài xế phù hợp dựa trên vị trí, trạng thái và tiêu chí vận hành. |
| 4 | **Quản lý chuyến đi & vị trí** | Tài xế nhận chuyến, cập nhật trạng thái từ đến điểm đón, đón khách, đang di chuyển đến hoàn thành; cập nhật vị trí để hỗ trợ theo dõi và dự kiến thời gian đến. |
| 5 | **Tính cước & thanh toán** | Tính số tiền phải trả sau chuyến; hỗ trợ thanh toán tiền mặt và thanh toán điện tử thông qua Payment Provider; xử lý kết quả giao dịch. |
| 6 | **Thông báo** | Gửi thông báo cho khách hàng và tài xế về yêu cầu đặt xe, nhận chuyến, trạng thái chuyến, hoàn thành chuyến và kết quả thanh toán. |
| 7 | **Đánh giá & lịch sử chuyến** | Khách hàng xem lịch sử chuyến, số tiền phải trả và đánh giá tài xế sau khi hoàn thành chuyến. |
| 8 | **Quản lý vận hành** | Nhân viên vận hành quản lý khách hàng, tài xế, phương tiện, chuyến đi; theo dõi chuyến đang diễn ra và xử lý các trường hợp phát sinh. |
| 9 | **Quản lý giao dịch & báo cáo** | Tra cứu lịch sử giao dịch và cung cấp báo cáo cơ bản về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| 10 | **Bảo mật & phân quyền** | Xác thực người dùng, phân quyền nhân viên/quản trị viên, bảo vệ dữ liệu cá nhân, vị trí và giao dịch; lưu vết các thao tác quan trọng. |
# 5. Yêu cầu danh nghiệp
## Business Requirements

| ID | Module | Business Requirement |
| --- | --- | --- |
| **BR-01** | **Quản lý tài khoản & hồ sơ** | Hệ thống phải hỗ trợ quản lý tài khoản, hồ sơ khách hàng, tài xế và thông tin phương tiện. |
| **BR-02** | **Đặt xe** | Hệ thống phải hỗ trợ khách hàng tạo yêu cầu đặt xe dựa trên điểm đón, điểm đến và loại xe. |
| **BR-03** | **Tìm tài xế** | Hệ thống phải tự động tìm kiếm và phân công tài xế phù hợp dựa trên vị trí, trạng thái và các tiêu chí vận hành. |
| **BR-04** | **Quản lý chuyến đi & vị trí** | Hệ thống phải hỗ trợ quản lý chuyến đi, cập nhật trạng thái và vị trí tài xế trong quá trình thực hiện chuyến. |
| **BR-05** | **Tính cước & thanh toán** | Hệ thống phải hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc thanh toán điện tử thông qua nhà cung cấp thanh toán bên ngoài. |
| **BR-06** | **Thông báo** | Hệ thống phải cung cấp cơ chế thông báo cho khách hàng và tài xế về các sự kiện quan trọng trong quá trình đặt và thực hiện chuyến. |
| **BR-07** | **Đánh giá & lịch sử chuyến** | Hệ thống phải hỗ trợ khách hàng tra cứu lịch sử chuyến, số tiền đã thanh toán và đánh giá tài xế sau khi hoàn thành chuyến. |
| **BR-08** | **Quản lý vận hành** | Hệ thống phải hỗ trợ nhân viên vận hành quản lý và giám sát khách hàng, tài xế, phương tiện và chuyến đi, đồng thời xử lý các trường hợp phát sinh. |
| **BR-09** | **Quản lý giao dịch & báo cáo** | Hệ thống phải hỗ trợ quản lý, tra cứu giao dịch và cung cấp các báo cáo phục vụ theo dõi hoạt động kinh doanh và hiệu quả vận hành. |
| **BR-10** | **Bảo mật & phân quyền** | Hệ thống phải đảm bảo xác thực người dùng, kiểm soát quyền truy cập, bảo vệ dữ liệu và lưu vết các thao tác quản trị quan trọng. |
## BR-01 — Quản lý tài khoản & hồ sơ

**Business Requirement:** Hệ thống phải hỗ trợ quản lý tài khoản, hồ sơ khách hàng, tài xế và thông tin phương tiện.

| ID | Functional Requirement |
|---|---|
| **FR-01** | Hệ thống cho phép khách hàng đăng ký tài khoản. |
| **FR-02** | Hệ thống cho phép người dùng đăng nhập và đăng xuất. |
| **FR-03** | Hệ thống cho phép khách hàng cập nhật thông tin cá nhân. |
| **FR-04** | Hệ thống cho phép tài xế đăng ký hoặc được nhân viên vận hành tạo tài khoản. |
| **FR-05** | Hệ thống cho phép tài xế cập nhật thông tin hồ sơ và phương tiện. |
| **FR-06** | Hệ thống cho phép tài xế cập nhật trạng thái hoạt động. |

---

## BR-02 — Đặt xe

**Business Requirement:** Hệ thống phải hỗ trợ khách hàng tạo yêu cầu đặt xe dựa trên điểm đón, điểm đến và loại xe.

| ID | Functional Requirement |
|---|---|
| **FR-07** | Hệ thống cho phép khách hàng nhập điểm đón. |
| **FR-08** | Hệ thống cho phép khách hàng nhập điểm đến. |
| **FR-09** | Hệ thống cho phép khách hàng lựa chọn loại xe. |
| **FR-10** | Hệ thống hiển thị thông tin chuyến trước khi khách hàng xác nhận đặt xe. |
| **FR-11** | Hệ thống cho phép khách hàng xác nhận và tạo yêu cầu đặt xe. |

---

## BR-03 — Tìm tài xế

**Business Requirement:** Hệ thống phải tự động tìm kiếm và phân công tài xế phù hợp dựa trên vị trí, trạng thái và các tiêu chí vận hành.

| ID | Functional Requirement |
|---|---|
| **FR-12** | Hệ thống xác định các tài xế đang sẵn sàng nhận chuyến. |
| **FR-13** | Hệ thống xác định tài xế phù hợp dựa trên vị trí, trạng thái và loại xe. |
| **FR-14** | Hệ thống ưu tiên tài xế phù hợp và gần khách hàng. |
| **FR-15** | Hệ thống gửi yêu cầu chuyến đến tài xế được lựa chọn. |
| **FR-16** | Hệ thống ghi nhận tài xế được phân công cho chuyến. |
| **FR-17** | Hệ thống tiếp tục tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. |
| **FR-18** | Hệ thống thông báo cho khách hàng khi không tìm được tài xế. |

---

## BR-04 — Quản lý chuyến đi & vị trí

**Business Requirement:** Hệ thống phải hỗ trợ quản lý chuyến đi, cập nhật trạng thái và vị trí tài xế trong quá trình thực hiện chuyến.

| ID | Functional Requirement |
|---|---|
| **FR-19** | Hệ thống cho phép tài xế chấp nhận hoặc từ chối chuyến. |
| **FR-20** | Hệ thống tạo và quản lý trạng thái của chuyến đi. |
| **FR-21** | Hệ thống cho phép tài xế cập nhật trạng thái đã đến điểm đón. |
| **FR-22** | Hệ thống cho phép tài xế cập nhật trạng thái đã đón khách. |
| **FR-23** | Hệ thống cho phép tài xế cập nhật trạng thái đang di chuyển. |
| **FR-24** | Hệ thống cho phép tài xế cập nhật trạng thái hoàn thành chuyến. |
| **FR-25** | Hệ thống ghi nhận và cập nhật vị trí của tài xế trong quá trình thực hiện chuyến. |
| **FR-26** | Hệ thống cho phép khách hàng theo dõi trạng thái chuyến đi. |

---

## BR-05 — Tính cước & thanh toán

**Business Requirement:** Hệ thống phải hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc thanh toán điện tử thông qua nhà cung cấp thanh toán bên ngoài.

| ID | Functional Requirement |
|---|---|
| **FR-27** | Hệ thống xác định số tiền khách hàng phải thanh toán. |
| **FR-28** | Hệ thống tính cước dựa trên loại dịch vụ và thông tin chuyến đi. |
| **FR-29** | Hệ thống cho phép khách hàng lựa chọn phương thức thanh toán. |
| **FR-30** | Hệ thống gửi yêu cầu thanh toán điện tử đến nhà cung cấp thanh toán. |
| **FR-31** | Hệ thống ghi nhận kết quả giao dịch thanh toán. |
| **FR-32** | Hệ thống thông báo cho khách hàng khi thanh toán thất bại. |

---

## BR-06 — Thông báo

**Business Requirement:** Hệ thống phải cung cấp cơ chế thông báo cho khách hàng và tài xế về các sự kiện quan trọng trong quá trình đặt và thực hiện chuyến.

| ID | Functional Requirement |
|---|---|
| **FR-33** | Hệ thống gửi thông báo khi yêu cầu đặt xe được tiếp nhận. |
| **FR-34** | Hệ thống gửi thông báo khi tài xế nhận chuyến. |
| **FR-35** | Hệ thống gửi thông báo khi tài xế đến điểm đón. |
| **FR-36** | Hệ thống gửi thông báo khi chuyến đi hoàn thành. |
| **FR-37** | Hệ thống gửi thông báo về kết quả thanh toán. |
| **FR-38** | Hệ thống gửi thông báo về chuyến mới hoặc thay đổi liên quan đến chuyến cho tài xế. |

---

## BR-07 — Đánh giá & lịch sử chuyến

**Business Requirement:** Hệ thống phải hỗ trợ khách hàng tra cứu lịch sử chuyến, số tiền đã thanh toán và đánh giá tài xế sau khi hoàn thành chuyến.

| ID | Functional Requirement |
|---|---|
| **FR-39** | Hệ thống cho phép khách hàng xem lịch sử chuyến đi. |
| **FR-40** | Hệ thống hiển thị số tiền phải thanh toán của từng chuyến. |
| **FR-41** | Hệ thống cho phép khách hàng đánh giá tài xế sau khi hoàn thành chuyến. |

---

## BR-08 — Quản lý vận hành

**Business Requirement:** Hệ thống phải hỗ trợ nhân viên vận hành quản lý và giám sát khách hàng, tài xế, phương tiện và chuyến đi, đồng thời xử lý các trường hợp phát sinh.

| ID | Functional Requirement |
|---|---|
| **FR-42** | Hệ thống cho phép nhân viên vận hành quản lý thông tin khách hàng. |
| **FR-43** | Hệ thống cho phép nhân viên vận hành quản lý thông tin tài xế. |
| **FR-44** | Hệ thống cho phép nhân viên vận hành quản lý thông tin phương tiện. |
| **FR-45** | Hệ thống cho phép nhân viên vận hành xem các chuyến đang diễn ra. |
| **FR-46** | Hệ thống cho phép nhân viên vận hành theo dõi trạng thái tài xế. |
| **FR-47** | Hệ thống cho phép nhân viên vận hành xử lý các trường hợp chuyến đi gặp sự cố. |

---

## BR-09 — Quản lý giao dịch & báo cáo

**Business Requirement:** Hệ thống phải hỗ trợ quản lý, tra cứu giao dịch và cung cấp các báo cáo phục vụ theo dõi hoạt động kinh doanh và hiệu quả vận hành.

| ID | Functional Requirement |
|---|---|
| **FR-48** | Hệ thống lưu trữ thông tin giao dịch thanh toán. |
| **FR-49** | Hệ thống cho phép nhân viên có quyền tra cứu lịch sử giao dịch. |
| **FR-50** | Hệ thống cung cấp báo cáo về số lượng chuyến. |
| **FR-51** | Hệ thống cung cấp báo cáo về doanh thu. |
| **FR-52** | Hệ thống cung cấp báo cáo về tỷ lệ chuyến hoàn thành và tỷ lệ hủy. |
| **FR-53** | Hệ thống cung cấp báo cáo về hiệu quả hoạt động của tài xế. |

---

## BR-10 — Bảo mật & phân quyền

**Business Requirement:** Hệ thống phải đảm bảo xác thực người dùng, kiểm soát quyền truy cập, bảo vệ dữ liệu và lưu vết các thao tác quản trị quan trọng.

| ID | Functional Requirement |
|---|---|
| **FR-54** | Hệ thống xác thực người dùng trước khi sử dụng các chức năng yêu cầu tài khoản. |
| **FR-55** | Hệ thống kiểm soát quyền truy cập các chức năng theo vai trò người dùng. |
| **FR-56** | Hệ thống bảo vệ thông tin cá nhân, thông tin phương tiện, dữ liệu vị trí và dữ liệu giao dịch. |
| **FR-57** | Hệ thống ghi nhận các thao tác quản trị quan trọng để phục vụ kiểm tra và xử lý sự cố. |
# 7. Vẽ Usecase 
```mermaid
flowchart LR

    KH["👤 Customer"]
    TX["🚕 Driver"]
    NV["👤 Operations Staff"]

    subgraph CAB["CAB SYSTEM"]

        UC01(["Quản lý tài khoản & hồ sơ"])
        UC02(["Đặt xe"])
        UC03(["Tìm & phân công tài xế"])
        UC04(["Quản lý chuyến đi"])
        UC05(["Theo dõi chuyến đi"])
        UC06(["Tính cước & thanh toán"])
        UC07(["Quản lý thông báo"])
        UC08(["Đánh giá & lịch sử chuyến"])
        UC09(["Quản lý vận hành"])
        UC10(["Quản lý giao dịch & báo cáo"])
        UC11(["Bảo mật & phân quyền"])

    end

    %% Customer
    KH --- UC01
    KH --- UC02
    KH --- UC05
    KH --- UC06
    KH --- UC07
    KH --- UC08

    %% Driver
    TX --- UC01
    TX --- UC04
    TX --- UC05
    TX --- UC07

    %% Operations Staff
    NV --- UC09
    NV --- UC10
    NV --- UC11
```
# 8. Đặc tả Usecase
# 8. Use Case Specification

## UC01 – Quản lý tài khoản & hồ sơ

| Thành phần         | Nội dung                                                                     |
| ------------------ | ---------------------------------------------------------------------------- |
| **Tên Use Case**   | Quản lý tài khoản & hồ sơ                                                    |
| **Actor**          | Khách hàng, Tài xế                                                          |
| **Mục tiêu**       | Cho phép khách hàng và tài xế đăng ký, đăng nhập và quản lý thông tin hồ sơ. |
| **Tiền điều kiện** | Người dùng chưa có tài khoản hoặc đã có tài khoản trong hệ thống.            |
| **Hậu điều kiện**  | Tài khoản hoặc thông tin hồ sơ được cập nhật thành công.                     |

### Luồng chính

| Actor                                                 | Hệ thống                               |
| ----------------------------------------------------- | -------------------------------------- |
| Người dùng chọn đăng ký hoặc đăng nhập.               | Hiển thị giao diện đăng ký/đăng nhập.  |
| Người dùng nhập thông tin tài khoản.                  | Kiểm tra thông tin được cung cấp.      |
| Người dùng xác nhận.                                  | Tạo tài khoản hoặc xác thực tài khoản. |
| Người dùng chọn cập nhật hồ sơ và nhập thông tin mới. | Kiểm tra và lưu thông tin hồ sơ.       |
|                                                       | Thông báo kết quả cho người dùng.      |

### Luồng ngoại lệ

* Thông tin đăng ký không hợp lệ → Hệ thống yêu cầu nhập lại.
* Thông tin đăng nhập không chính xác → Hệ thống thông báo đăng nhập thất bại.

---

## UC02 – Đặt xe

| Thành phần         | Nội dung                                                |
| ------------------ | ------------------------------------------------------- |
| **Tên Use Case**   | Đặt xe                                                  |
| **Actor**          | Khách hàng                                              |
| **Mục tiêu**       | Cho phép khách hàng tạo yêu cầu đặt xe.                 |
| **Tiền điều kiện** | Khách hàng đã đăng nhập.                                |
| **Hậu điều kiện**  | Yêu cầu đặt xe được tạo và chuyển sang bước tìm tài xế. |

### Luồng chính

| Actor                                        | Hệ thống                                               |
| -------------------------------------------- | ------------------------------------------------------ |
| Khách hàng nhập điểm đón.                    | Ghi nhận điểm đón.                                     |
| Khách hàng nhập điểm đến.                    | Ghi nhận điểm đến.                                     |
| Khách hàng lựa chọn loại xe.                 | Ghi nhận loại xe được chọn.                            |
| Khách hàng xem và xác nhận thông tin chuyến. | Kiểm tra thông tin đặt xe.                             |
|                                              | Tạo yêu cầu đặt xe.                                    |
|                                              | Chuyển yêu cầu sang quá trình tìm và phân công tài xế. |

### Luồng ngoại lệ

* Thông tin chuyến không hợp lệ → Hệ thống yêu cầu khách hàng nhập lại.
* Không thể tạo yêu cầu → Hệ thống thông báo cho khách hàng.

---

## UC03 – Tìm & phân công tài xế

| Thành phần         | Nội dung                                                                    |
| ------------------ | --------------------------------------------------------------------------- |
| **Tên Use Case**   | Tìm & phân công tài xế                                                      |
| **Actor**          | Tài xế                                                                      |
| **Mục tiêu**       | Tìm và phân công tài xế phù hợp cho yêu cầu đặt xe.                         |
| **Tiền điều kiện** | Có yêu cầu đặt xe.                                                          |
| **Hậu điều kiện**  | Tài xế được phân công hoặc khách hàng được thông báo không tìm được tài xế. |

### Luồng chính

| Actor                            | Hệ thống                                                                      |
| -------------------------------- | ----------------------------------------------------------------------------- |
|                                  | Tiếp nhận yêu cầu đặt xe.                                                     |
|                                  | Xác định các tài xế phù hợp dựa trên vị trí, trạng thái và tiêu chí vận hành. |
|                                  | Ưu tiên tài xế phù hợp và gần khách hàng.                                     |
| Tài xế nhận được yêu cầu chuyến. | Gửi yêu cầu chuyến đến tài xế phù hợp.                                        |
| Tài xế chấp nhận chuyến.         | Ghi nhận tài xế được phân công.                                               |
|                                  | Cập nhật thông tin chuyến cho khách hàng.                                     |

### Luồng ngoại lệ

* Tài xế từ chối hoặc không phản hồi → Hệ thống tiếp tục tìm tài xế khác.
* Không tìm được tài xế → Hệ thống thông báo cho khách hàng.

---

## UC04 – Quản lý chuyến đi

| Thành phần         | Nội dung                                                                 |
| ------------------ | ------------------------------------------------------------------------ |
| **Tên Use Case**   | Quản lý chuyến đi                                                        |
| **Actor**          | Tài xế                                                                   |
| **Mục tiêu**       | Cho phép tài xế thực hiện và cập nhật trạng thái chuyến đi.              |
| **Tiền điều kiện** | Tài xế đã được phân công cho chuyến.                                     |
| **Hậu điều kiện**  | Trạng thái chuyến được cập nhật đến khi hoàn thành hoặc phát sinh sự cố. |

### Luồng chính

| Actor                              | Hệ thống                          |
| ---------------------------------- | --------------------------------- |
| Tài xế nhận chuyến.                | Ghi nhận tài xế thực hiện chuyến. |
| Tài xế cập nhật đã đến điểm đón.   | Cập nhật trạng thái chuyến.       |
| Tài xế cập nhật đã đón khách.      | Cập nhật trạng thái chuyến.       |
| Tài xế cập nhật đang di chuyển.    | Cập nhật trạng thái chuyến.       |
| Tài xế cập nhật hoàn thành chuyến. | Ghi nhận chuyến đã hoàn thành.    |

### Luồng ngoại lệ

* Chuyến gặp sự cố → Hệ thống ghi nhận sự cố để nhân viên vận hành xử lý.

---

## UC05 – Theo dõi chuyến đi

| Thành phần         | Nội dung                                                                      |
| ------------------ | ----------------------------------------------------------------------------- |
| **Tên Use Case**   | Theo dõi chuyến đi                                                            |
| **Actor**          | Khách hàng                                                                    |
| **Mục tiêu**       | Cho phép khách hàng theo dõi trạng thái và vị trí của tài xế trong chuyến đi. |
| **Tiền điều kiện** | Khách hàng có chuyến đang được thực hiện.                                     |
| **Hậu điều kiện**  | Khách hàng nhận được thông tin cập nhật về chuyến đi.                         |

### Luồng chính

| Actor                           | Hệ thống                                                           |
| ------------------------------- | ------------------------------------------------------------------ |
| Khách hàng mở thông tin chuyến. | Hiển thị trạng thái hiện tại của chuyến.                           |
|                                 | Cập nhật vị trí tài xế.                                            |
|                                 | Hiển thị thông tin tài xế và thời gian dự kiến đến khi có dữ liệu. |
| Khách hàng theo dõi chuyến.     | Cập nhật thông tin chuyến theo dữ liệu mới.                        |

### Luồng ngoại lệ

* Không nhận được dữ liệu vị trí → Hệ thống hiển thị thông tin vị trí gần nhất.

---

## UC06 – Tính cước & thanh toán

| Thành phần         | Nội dung                                                   |
| ------------------ | ---------------------------------------------------------- |
| **Tên Use Case**   | Tính cước & thanh toán                                     |
| **Actor**          | Khách hàng                                                 |
| **Mục tiêu**       | Xác định số tiền phải trả và hỗ trợ khách hàng thanh toán. |
| **Tiền điều kiện** | Chuyến đi đã hoàn thành.                                   |
| **Hậu điều kiện**  | Kết quả thanh toán được ghi nhận.                          |

### Luồng chính

| Actor                                   | Hệ thống                                            |
| --------------------------------------- | --------------------------------------------------- |
|                                         | Xác định số tiền khách hàng phải trả.               |
| Khách hàng chọn phương thức thanh toán. | Ghi nhận phương thức thanh toán.                    |
| Khách hàng xác nhận thanh toán điện tử. | Gửi yêu cầu thanh toán đến nhà cung cấp thanh toán. |
|                                         | Nhận kết quả giao dịch.                             |
|                                         | Ghi nhận kết quả thanh toán.                        |
| Khách hàng thanh toán tiền mặt.         | Ghi nhận phương thức thanh toán tiền mặt.           |

### Luồng ngoại lệ

* Thanh toán điện tử thất bại → Hệ thống thông báo cho khách hàng và xử lý lại theo chính sách doanh nghiệp.

---

## UC07 – Quản lý thông báo

| Thành phần         | Nội dung                                                                              |
| ------------------ | ------------------------------------------------------------------------------------- |
| **Tên Use Case**   | Quản lý thông báo                                                                     |
| **Actor**          | Khách hàng, Tài xế                                                                    |
| **Mục tiêu**       | Cung cấp thông báo về các sự kiện quan trọng trong quá trình đặt và thực hiện chuyến. |
| **Tiền điều kiện** | Có sự kiện cần thông báo.                                                             |
| **Hậu điều kiện**  | Thông báo được gửi đến đối tượng liên quan.                                           |

### Luồng chính

| Actor                             | Hệ thống                            |
| --------------------------------- | ----------------------------------- |
|                                   | Phát sinh sự kiện cần thông báo.    |
|                                   | Xác định đối tượng nhận thông báo.  |
|                                   | Gửi thông báo qua kênh được hỗ trợ. |
| Khách hàng/Tài xế nhận thông báo. | Ghi nhận trạng thái gửi thông báo.  |

### Luồng ngoại lệ

* Kênh thông báo gặp lỗi → Hệ thống ghi nhận lỗi và xử lý theo cơ chế phù hợp.

---

## UC08 – Đánh giá & lịch sử chuyến

| Thành phần         | Nội dung                                                        |
| ------------------ | --------------------------------------------------------------- |
| **Tên Use Case**   | Đánh giá & lịch sử chuyến                                       |
| **Actor**          | Khách hàng                                                      |
| **Mục tiêu**       | Cho phép khách hàng xem lịch sử chuyến và đánh giá tài xế.      |
| **Tiền điều kiện** | Khách hàng đã đăng nhập.                                        |
| **Hậu điều kiện**  | Lịch sử chuyến được hiển thị hoặc đánh giá được lưu thành công. |

### Luồng chính

| Actor                            | Hệ thống                                       |
| -------------------------------- | ---------------------------------------------- |
| Khách hàng mở lịch sử chuyến.    | Hiển thị danh sách chuyến đã thực hiện.        |
| Khách hàng chọn một chuyến.      | Hiển thị thông tin chuyến và số tiền phải trả. |
| Khách hàng chọn đánh giá tài xế. | Hiển thị chức năng đánh giá.                   |
| Khách hàng gửi đánh giá.         | Kiểm tra và lưu đánh giá.                      |

### Luồng ngoại lệ

* Chuyến chưa hoàn thành → Hệ thống không cho phép đánh giá.

---

## UC09 – Quản lý vận hành

| Thành phần         | Nội dung                                                      |
| ------------------ | ------------------------------------------------------------- |
| **Tên Use Case**   | Quản lý vận hành                                              |
| **Actor**          | Nhân viên vận hành                                            |
| **Mục tiêu**       | Hỗ trợ nhân viên quản lý và giám sát hoạt động của hệ thống.  |
| **Tiền điều kiện** | Nhân viên đã đăng nhập và có quyền phù hợp.                   |
| **Hậu điều kiện**  | Thông tin được cập nhật hoặc trường hợp phát sinh được xử lý. |

### Luồng chính

| Actor                                           | Hệ thống                                       |
| ----------------------------------------------- | ---------------------------------------------- |
| Nhân viên vận hành truy cập giao diện quản trị. | Kiểm tra quyền truy cập và hiển thị giao diện. |
| Nhân viên quản lý thông tin khách hàng.         | Cập nhật thông tin khách hàng.                 |
| Nhân viên quản lý thông tin tài xế.             | Cập nhật thông tin tài xế.                     |
| Nhân viên quản lý phương tiện.                  | Cập nhật thông tin phương tiện.                |
| Nhân viên xem các chuyến đang diễn ra.          | Hiển thị trạng thái chuyến và tài xế.          |
| Nhân viên xử lý trường hợp phát sinh.           | Ghi nhận và cập nhật kết quả xử lý.            |

### Luồng ngoại lệ

* Nhân viên không có quyền → Hệ thống từ chối thao tác.
* Chuyến không thể xử lý → Hệ thống ghi nhận sự cố.

---

## UC10 – Quản lý giao dịch & báo cáo

| Thành phần         | Nội dung                                                   |
| ------------------ | ---------------------------------------------------------- |
| **Tên Use Case**   | Quản lý giao dịch & báo cáo                                |
| **Actor**          | Nhân viên vận hành                                         |
| **Mục tiêu**       | Hỗ trợ tra cứu giao dịch và theo dõi hoạt động kinh doanh. |
| **Tiền điều kiện** | Nhân viên đã đăng nhập và có quyền truy cập.               |
| **Hậu điều kiện**  | Thông tin giao dịch hoặc báo cáo được hiển thị.            |

### Luồng chính

| Actor                                   | Hệ thống                                                                                  |
| --------------------------------------- | ----------------------------------------------------------------------------------------- |
| Nhân viên truy cập chức năng giao dịch. | Hiển thị lịch sử giao dịch.                                                               |
| Nhân viên tra cứu giao dịch.            | Tìm kiếm và hiển thị kết quả.                                                             |
| Nhân viên chọn loại báo cáo.            | Tổng hợp dữ liệu tương ứng.                                                               |
|                                         | Hiển thị báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |

### Luồng ngoại lệ

* Không có dữ liệu → Hệ thống thông báo không có dữ liệu phù hợp.

---

## UC11 – Bảo mật & phân quyền

| Thành phần         | Nội dung                                                                               |
| ------------------ | -------------------------------------------------------------------------------------- |
| **Tên Use Case**   | Bảo mật & phân quyền                                                                   |
| **Actor**          | Nhân viên vận hành                                                                     |
| **Mục tiêu**       | Đảm bảo người dùng được xác thực và chỉ thực hiện các chức năng phù hợp với quyền hạn. |
| **Tiền điều kiện** | Người dùng yêu cầu truy cập hệ thống hoặc chức năng cần xác thực.                      |
| **Hậu điều kiện**  | Quyền truy cập được kiểm tra và các thao tác quan trọng được ghi nhận.                 |

### Luồng chính

| Actor                                   | Hệ thống                                    |
| --------------------------------------- | ------------------------------------------- |
| Người dùng nhập thông tin đăng nhập.    | Xác thực thông tin người dùng.              |
|                                         | Xác định vai trò và quyền truy cập.         |
| Người dùng truy cập chức năng.          | Kiểm tra quyền trước khi cho phép thao tác. |
| Người dùng thực hiện thao tác quản trị. | Ghi nhận thao tác quan trọng vào nhật ký.   |

### Luồng ngoại lệ

* Thông tin xác thực không hợp lệ → Hệ thống từ chối đăng nhập.
* Người dùng không có quyền → Hệ thống từ chối thao tác.

# 9. Phân tích quy trình nghiệp vụ
# 9. Phân tích quy trình nghiệp vụ

Phân tích quy trình nghiệp vụ nhằm mô tả trình tự thực hiện các hoạt động chính của hệ thống CAB System và sự phối hợp giữa khách hàng, tài xế, hệ thống, nhân viên vận hành và các nhà cung cấp bên ngoài.

## 9.1. Quy trình đặt xe

```mermaid
flowchart LR

    subgraph KH["Khách hàng"]
        A(("Start"))
        B["Đăng nhập"]
        C["Nhập điểm đón"]
        D["Nhập điểm đến"]
        E["Chọn loại xe"]
        F["Xác nhận đặt xe"]
    end

    subgraph CAB["CAB System"]
        G["Kiểm tra thông tin đặt xe"]
        H{"Thông tin hợp lệ?"}
        I["Tạo yêu cầu đặt xe"]
        J["Thông báo tiếp nhận yêu cầu"]
    end

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H

    H -- "Không" --> C
    H -- "Có" --> I
    I --> J
    J --> K(("Chuyển sang quy trình tìm tài xế"))
```

### Mô tả

| STT | Đối tượng  | Hoạt động                                                |
| --: | ---------- | -------------------------------------------------------- |
|   1 | Khách hàng | Đăng nhập vào hệ thống.                                  |
|   2 | Khách hàng | Nhập điểm đón và điểm đến.                               |
|   3 | Khách hàng | Lựa chọn loại xe.                                        |
|   4 | Khách hàng | Xác nhận thông tin đặt xe.                               |
|   5 | Hệ thống   | Kiểm tra thông tin đặt xe.                               |
|   6 | Hệ thống   | Nếu thông tin không hợp lệ, yêu cầu khách hàng nhập lại. |
|   7 | Hệ thống   | Nếu thông tin hợp lệ, tạo yêu cầu đặt xe.                |
|   8 | Hệ thống   | Thông báo hệ thống đã tiếp nhận yêu cầu.                 |
|   9 | Hệ thống   | Chuyển yêu cầu sang quy trình tìm và phân công tài xế.   |

---

## 9.2. Quy trình tìm và phân công tài xế

```mermaid
flowchart LR

    A(("Nhận yêu cầu đặt xe"))

    subgraph CAB["CAB System"]
        B["Xác định tài xế đang sẵn sàng"]
        C["Lọc tài xế phù hợp"]
        D["Ưu tiên tài xế phù hợp và gần khách hàng"]
        E{"Có tài xế phù hợp?"}
        F["Gửi yêu cầu chuyến"]
        G{"Tài xế phản hồi?"}
        H{"Tài xế chấp nhận?"}
        I["Ghi nhận tài xế được phân công"]
        J["Thông báo tài xế cho khách hàng"]
        K["Tiếp tục tìm tài xế khác"]
        L["Thông báo không tìm được tài xế"]
    end

    A --> B
    B --> C
    C --> D
    D --> E

    E -- "Không" --> L
    E -- "Có" --> F

    F --> G
    G -- "Không" --> K
    G -- "Có" --> H

    H -- "Không" --> K
    H -- "Có" --> I

    K --> B
    I --> J
    J --> M(("Chuyển sang thực hiện chuyến"))
    L --> N(("End"))
```

### Mô tả

| STT | Đối tượng | Hoạt động                                                         |
| --: | --------- | ----------------------------------------------------------------- |
|   1 | Hệ thống  | Xác định các tài xế đang sẵn sàng.                                |
|   2 | Hệ thống  | Lọc tài xế phù hợp dựa trên vị trí, trạng thái và loại xe.        |
|   3 | Hệ thống  | Ưu tiên tài xế phù hợp và gần khách hàng.                         |
|   4 | Hệ thống  | Kiểm tra có tài xế phù hợp hay không.                             |
|   5 | Hệ thống  | Gửi yêu cầu chuyến đến tài xế được lựa chọn.                      |
|   6 | Tài xế    | Nhận và phản hồi yêu cầu chuyến.                                  |
|   7 | Hệ thống  | Nếu tài xế từ chối hoặc không phản hồi, tiếp tục tìm tài xế khác. |
|   8 | Hệ thống  | Nếu tài xế chấp nhận, ghi nhận tài xế được phân công.             |
|   9 | Hệ thống  | Thông báo thông tin tài xế cho khách hàng.                        |
|  10 | Hệ thống  | Nếu không còn tài xế phù hợp, thông báo cho khách hàng.           |

---

## 9.3. Quy trình thực hiện chuyến đi

```mermaid
flowchart LR

    A(("Tài xế được phân công"))

    subgraph TX["Tài xế"]
        B["Nhận chuyến"]
        C["Di chuyển đến điểm đón"]
        D["Cập nhật đã đến điểm đón"]
        E["Đón khách"]
        F["Cập nhật đã đón khách"]
        G["Thực hiện chuyến đi"]
        H["Cập nhật vị trí"]
        I["Cập nhật đang di chuyển"]
        J["Hoàn thành chuyến"]
    end

    subgraph CAB["CAB System"]
        K["Cập nhật trạng thái chuyến"]
        L["Cập nhật vị trí tài xế"]
        M["Thông báo trạng thái cho khách hàng"]
        N["Ghi nhận chuyến hoàn thành"]
    end

    A --> B
    B --> C
    C --> D
    D --> K
    K --> M

    D --> E
    E --> F
    F --> K
    K --> M

    F --> G
    G --> H
    H --> L
    L --> M
    M --> G

    G --> I
    I --> K

    G --> J
    J --> N
    N --> O(("Chuyển sang tính cước"))
```

### Mô tả

| STT | Đối tượng | Hoạt động                                               |
| --: | --------- | ------------------------------------------------------- |
|   1 | Tài xế    | Nhận chuyến đã được phân công.                          |
|   2 | Tài xế    | Di chuyển đến điểm đón.                                 |
|   3 | Tài xế    | Cập nhật trạng thái đã đến điểm đón.                    |
|   4 | Hệ thống  | Cập nhật trạng thái chuyến và thông báo cho khách hàng. |
|   5 | Tài xế    | Đón khách và cập nhật trạng thái.                       |
|   6 | Tài xế    | Thực hiện chuyến đi.                                    |
|   7 | Tài xế    | Cập nhật vị trí trong quá trình di chuyển.              |
|   8 | Hệ thống  | Cập nhật vị trí và trạng thái để khách hàng theo dõi.   |
|   9 | Tài xế    | Cập nhật trạng thái hoàn thành chuyến.                  |
|  10 | Hệ thống  | Ghi nhận chuyến đã hoàn thành.                          |

---

## 9.4. Quy trình tính cước và thanh toán

```mermaid
flowchart LR

    A(("Chuyến đi hoàn thành"))

    subgraph CAB["CAB System"]
        B["Xác định thông tin chuyến"]
        C["Tính cước"]
        D["Hiển thị số tiền phải trả"]
        E{"Phương thức thanh toán?"}
        F["Ghi nhận thanh toán tiền mặt"]
        G["Gửi yêu cầu thanh toán điện tử"]
        H{"Thanh toán thành công?"}
        I["Ghi nhận giao dịch"]
        J["Thông báo thanh toán thất bại"]
        K["Xử lý lại theo chính sách"]
    end

    subgraph KH["Khách hàng"]
        L["Chọn phương thức thanh toán"]
    end

    subgraph PP["Payment Provider"]
        M["Xử lý giao dịch"]
        N["Trả kết quả giao dịch"]
    end

    A --> B
    B --> C
    C --> D
    D --> L
    L --> E

    E -- "Tiền mặt" --> F
    F --> O(("Hoàn tất thanh toán"))

    E -- "Điện tử" --> G
    G --> M
    M --> N
    N --> H

    H -- "Có" --> I
    I --> O

    H -- "Không" --> J
    J --> K
    K --> O
```

### Mô tả

| STT | Đối tượng        | Hoạt động                                                 |
| --: | ---------------- | --------------------------------------------------------- |
|   1 | Hệ thống         | Xác định thông tin chuyến đã hoàn thành.                  |
|   2 | Hệ thống         | Tính số tiền khách hàng phải trả.                         |
|   3 | Hệ thống         | Hiển thị số tiền phải thanh toán.                         |
|   4 | Khách hàng       | Lựa chọn phương thức thanh toán.                          |
|   5 | Hệ thống         | Nếu thanh toán tiền mặt, ghi nhận phương thức thanh toán. |
|   6 | Hệ thống         | Nếu thanh toán điện tử, gửi yêu cầu đến Payment Provider. |
|   7 | Payment Provider | Xử lý giao dịch và trả kết quả.                           |
|   8 | Hệ thống         | Ghi nhận giao dịch nếu thanh toán thành công.             |
|   9 | Hệ thống         | Thông báo cho khách hàng nếu thanh toán thất bại.         |
|  10 | Hệ thống         | Cho phép xử lý lại theo chính sách doanh nghiệp.          |

---

## 9.5. Quy trình thông báo

```mermaid
flowchart LR

    A(("Phát sinh sự kiện"))

    subgraph CAB["CAB System"]
        B["Xác định loại sự kiện"]
        C["Xác định đối tượng nhận"]
        D["Tạo nội dung thông báo"]
        E["Chọn kênh thông báo"]
        F["Gửi thông báo"]
        G{"Gửi thành công?"}
        H["Ghi nhận trạng thái gửi"]
        I["Ghi nhận lỗi"]
        J["Xử lý theo cơ chế phù hợp"]
    end

    subgraph N["Notification Provider"]
        K["Gửi SMS / Email / Push"]
        L["Trả kết quả gửi"]
    end

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> K
    K --> L
    L --> G

    G -- "Có" --> H
    G -- "Không" --> I
    I --> J
```

### Mô tả

| STT | Đối tượng             | Hoạt động                                       |
| --: | --------------------- | ----------------------------------------------- |
|   1 | Hệ thống              | Phát sinh sự kiện cần thông báo.                |
|   2 | Hệ thống              | Xác định đối tượng nhận thông báo.              |
|   3 | Hệ thống              | Tạo nội dung thông báo.                         |
|   4 | Hệ thống              | Xác định kênh thông báo phù hợp.                |
|   5 | Hệ thống              | Gửi thông báo đến Notification Provider.        |
|   6 | Notification Provider | Gửi SMS, Email hoặc Push Notification.          |
|   7 | Notification Provider | Trả kết quả gửi về hệ thống.                    |
|   8 | Hệ thống              | Ghi nhận trạng thái nếu gửi thành công.         |
|   9 | Hệ thống              | Ghi nhận lỗi và xử lý phù hợp nếu gửi thất bại. |

---

## 9.6. Quy trình đánh giá và lịch sử chuyến

```mermaid
flowchart LR

    A(("Chuyến đi hoàn thành"))

    subgraph CAB["CAB System"]
        B["Lưu thông tin chuyến"]
        C["Lưu kết quả thanh toán"]
        D["Cập nhật lịch sử chuyến"]
        E["Hiển thị lịch sử chuyến"]
        F["Hiển thị thông tin chuyến"]
        G{"Chuyến đã hoàn thành?"}
        H["Lưu đánh giá"]
    end

    subgraph KH["Khách hàng"]
        I["Xem lịch sử chuyến"]
        J["Chọn chuyến"]
        K["Chọn đánh giá tài xế"]
        L["Gửi đánh giá"]
    end

    A --> B
    B --> C
    C --> D
    D --> E
    E --> I
    I --> J
    J --> F
    F --> K
    K --> G

    G -- "Có" --> L
    L --> H
    H --> M(("End"))

    G -- "Không" --> N["Không cho phép đánh giá"]
    N --> M
```

### Mô tả

| STT | Đối tượng  | Hoạt động                                       |
| --: | ---------- | ----------------------------------------------- |
|   1 | Hệ thống   | Lưu thông tin chuyến sau khi hoàn thành.        |
|   2 | Hệ thống   | Lưu kết quả thanh toán.                         |
|   3 | Hệ thống   | Cập nhật lịch sử chuyến của khách hàng.         |
|   4 | Khách hàng | Mở lịch sử chuyến.                              |
|   5 | Khách hàng | Chọn chuyến muốn xem.                           |
|   6 | Hệ thống   | Hiển thị thông tin chuyến và số tiền phải trả.  |
|   7 | Khách hàng | Chọn chức năng đánh giá tài xế.                 |
|   8 | Hệ thống   | Kiểm tra trạng thái chuyến.                     |
|   9 | Hệ thống   | Chỉ cho phép đánh giá nếu chuyến đã hoàn thành. |
|  10 | Hệ thống   | Lưu đánh giá của khách hàng.                    |

---

## 9.7. Quy trình quản lý và xử lý sự cố vận hành

```mermaid
flowchart LR

    A(("Phát sinh sự cố"))

    subgraph NV["Nhân viên vận hành"]
        B["Tiếp nhận sự cố"]
        C["Kiểm tra thông tin chuyến"]
        D["Kiểm tra trạng thái tài xế"]
        E["Xác định nguyên nhân"]
        F["Thực hiện xử lý"]
        G["Cập nhật kết quả xử lý"]
    end

    subgraph CAB["CAB System"]
        H["Cung cấp thông tin chuyến"]
        I["Cung cấp thông tin tài xế"]
        J["Ghi nhận sự cố"]
        K["Lưu lịch sử xử lý"]
    end

    A --> J
    J --> B
    B --> C
    C --> H
    H --> D
    D --> I
    I --> E
    E --> F
    F --> G
    G --> K
    K --> L(("End"))
```

### Mô tả

| STT | Đối tượng          | Hoạt động                                         |
| --: | ------------------ | ------------------------------------------------- |
|   1 | Hệ thống           | Ghi nhận trường hợp chuyến đi gặp sự cố.          |
|   2 | Nhân viên vận hành | Tiếp nhận và kiểm tra sự cố.                      |
|   3 | Nhân viên vận hành | Kiểm tra thông tin chuyến.                        |
|   4 | Nhân viên vận hành | Kiểm tra trạng thái tài xế.                       |
|   5 | Nhân viên vận hành | Xác định nguyên nhân và hướng xử lý.              |
|   6 | Nhân viên vận hành | Thực hiện xử lý sự cố.                            |
|   7 | Nhân viên vận hành | Cập nhật kết quả xử lý.                           |
|   8 | Hệ thống           | Lưu lịch sử xử lý để phục vụ kiểm tra và tra cứu. |

## 9.8. Tổng hợp các quy trình nghiệp vụ

Các quy trình nghiệp vụ chính của CAB System gồm:

| STT | Quy trình                            | Actor chính                              |
| --: | ------------------------------------ | ---------------------------------------- |
|   1 | Quy trình đặt xe                     | Khách hàng                               |
|   2 | Quy trình tìm và phân công tài xế    | CAB System, Tài xế                       |
|   3 | Quy trình thực hiện chuyến đi        | Tài xế, Khách hàng                       |
|   4 | Quy trình tính cước và thanh toán    | Khách hàng, CAB System, Payment Provider |
|   5 | Quy trình thông báo                  | CAB System, Notification Provider        |
|   6 | Quy trình đánh giá và lịch sử chuyến | Khách hàng, CAB System                   |
|   7 | Quy trình quản lý và xử lý sự cố     | Nhân viên vận hành, CAB System           |

Các quy trình trên thể hiện luồng nghiệp vụ chính của hệ thống, đồng thời liên kết với các yêu cầu chức năng BR-01 đến BR-10 đã xác định ở các phần trước.

# 10. Phân tích quy tắc nghiệp vụ 
| ID           | Quy tắc nghiệp vụ           | Mô tả                                                                                                              |
| ------------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **BRULE-01** | Xác thực người dùng         | Người dùng phải đăng nhập trước khi sử dụng các chức năng yêu cầu tài khoản.                                       |
| **BRULE-02** | Thông tin đặt xe            | Yêu cầu đặt xe phải có điểm đón, điểm đến và loại xe trước khi được xác nhận.                                      |
| **BRULE-03** | Tài xế sẵn sàng             | Chỉ tài xế đang ở trạng thái sẵn sàng mới được xem xét để nhận chuyến.                                             |
| **BRULE-04** | Tài xế phù hợp              | Tài xế được lựa chọn phải phù hợp với vị trí, trạng thái và loại xe yêu cầu.                                       |
| **BRULE-05** | Ưu tiên tài xế              | Hệ thống ưu tiên tài xế phù hợp và gần khách hàng theo tiêu chí vận hành.                                          |
| **BRULE-06** | Tài xế từ chối              | Nếu tài xế từ chối chuyến, hệ thống phải tiếp tục tìm tài xế khác.                                                 |
| **BRULE-07** | Tài xế không phản hồi       | Nếu tài xế không phản hồi trong thời gian quy định, hệ thống phải có cơ chế tiếp tục tìm tài xế khác.              |
| **BRULE-08** | Không tìm được tài xế       | Nếu không còn tài xế phù hợp, hệ thống phải thông báo rõ ràng cho khách hàng.                                      |
| **BRULE-09** | Trạng thái chuyến           | Trạng thái chuyến phải được cập nhật theo tiến trình thực tế của chuyến đi.                                        |
| **BRULE-10** | Cập nhật vị trí             | Vị trí tài xế được ghi nhận trong quá trình thực hiện chuyến để hỗ trợ theo dõi.                                   |
| **BRULE-11** | Tính cước                   | Số tiền phải trả được xác định dựa trên loại dịch vụ và thông tin chuyến đi.                                       |
| **BRULE-12** | Phương thức thanh toán      | Khách hàng có thể thanh toán bằng tiền mặt hoặc phương thức thanh toán điện tử được hỗ trợ.                        |
| **BRULE-13** | Thanh toán điện tử          | Giao dịch điện tử phải được xử lý thông qua nhà cung cấp thanh toán bên ngoài.                                     |
| **BRULE-14** | Bảo vệ thông tin thanh toán | Hệ thống CAB không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.                             |
| **BRULE-15** | Thanh toán thất bại         | Khi thanh toán điện tử thất bại, hệ thống phải thông báo cho khách hàng và xử lý lại theo chính sách doanh nghiệp. |
| **BRULE-16** | Đánh giá tài xế             | Khách hàng chỉ được đánh giá tài xế sau khi chuyến đi hoàn thành.                                                  |
| **BRULE-17** | Phân quyền                  | Người dùng chỉ được thực hiện các chức năng phù hợp với vai trò và quyền được cấp.                                 |
| **BRULE-18** | Nhật ký thao tác            | Các thao tác quản trị quan trọng phải được ghi nhận để phục vụ kiểm tra và xử lý sự cố.                            |
| **BRULE-19** | Bảo vệ dữ liệu              | Thông tin cá nhân, phương tiện, vị trí và giao dịch phải được bảo vệ.                                              |
| **BRULE-20** | Báo cáo                     | Dữ liệu báo cáo phải được tổng hợp từ thông tin chuyến đi và giao dịch được hệ thống ghi nhận.                     |

