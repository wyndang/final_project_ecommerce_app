# ChitsTech Store (final_project)

Một dự án Flutter mới. Đây là một ứng dụng thương mại điện tử đa nền tảng, đầy đủ chức năng cho người mua và chủ cửa hàng, tập trung vào việc bán máy tính và linh kiện máy tính.

## Mục lục

1.  [Tổng quan](#tổng-quan)
2.  [Tính năng](#tính-năng)
    * [Tính năng cho Khách hàng](#tính-năng-cho-khách-hàng)
    * [Tính năng cho Quản trị viên](#tính-năng-cho-quản-trị-viên)
3.  [Công nghệ sử dụng](#công-nghệ-sử-dụng)
4.  [Cấu trúc Dự án](#cấu-trúc-dự-án)
5.  [Bắt đầu](#bắt-đầu)
    * [Điều kiện tiên quyết](#điều-kiện-tiên-quyết)
    * [Cài đặt](#cài-đặt)
6.  [Chạy Ứng dụng](#chạy-ứng-dụng)
7.  [Triển khai](#triển-khai)
8.  [Thông tin Đánh giá](#thông-tin-đánh-giá)
    * [Tài khoản có sẵn để đánh giá](#tài-khoản-có-sẵn-để-đánh-giá)
    * https://vi.ipshu.com/host_name(#url-và-thông-tin-máy-chủ)
    * [Lưu ý về Xây dựng và Chạy Dự án](#lưu-ý-về-xây-dựng-và-chạy-dự-án)
9.  [Yêu cầu Chính của Dự án](#yêu-cầu-chính-của-dự-án)
    * [Hợp tác Nhóm](#hợp-tác-nhóm)
    * [UI/UX](#uiux)
    * [Thiết kế Đáp ứng (Responsive Design)](#thiết-kế-đáp-ứng-responsive-design)
    * [Khả năng Hoạt động Ngoại tuyến (Offline Capability)](#khả-năng-hoạt-động-ngoại-tuyến-offline-capability)
10. [Tính năng Tùy chọn (Bonus)](#tính-năng-tùy-chọn-bonus)
11. [Liên hệ](#liên-hệ)

## Tổng quan

Dự án cuối kỳ của môn học "Phát triển ứng dụng di động đa nền tảng - 502071" bao gồm việc tạo ra một ứng dụng thương mại điện tử đa nền tảng, đầy đủ chức năng có tên "ChitsTech Store". Ứng dụng phục vụ cả người mua và chủ cửa hàng, với trọng tâm cụ thể là chỉ bán máy tính và linh kiện máy tính. Phần giao diện người dùng (front end) được phát triển bằng Flutter, và phần phụ trợ (backend) được triển khai bằng Appwrite.

Dự án nhằm kiểm tra kỹ năng phát triển Flutter và tích hợp backend, bao gồm các chức năng thiết yếu của thương mại điện tử như xác thực người dùng, quản lý sản phẩm và xử lý đơn hàng.

## Tính năng

Ứng dụng được chia thành các tính năng cho khách hàng và một bảng điều khiển quản trị cho chủ cửa hàng.

### Tính năng cho Khách hàng

* **Màn hình chính (Home Screen)**:
    * Hiển thị sản phẩm được phân loại thành "Sản phẩm Khuyến mãi", "Sản phẩm Mới," "Sản phẩm Bán chạy nhất," và ít nhất năm danh mục riêng biệt khác (ví dụ: máy tính xách tay, màn hình, ổ cứng, v.v.).
    * Sản phẩm được hiển thị dưới dạng lưới (grid view) trong mỗi mục.
    * Cho phép người dùng mua hàng mà không cần đăng nhập. Tài khoản sẽ tự động được tạo nếu chưa có, và lịch sử đơn hàng được lưu lại.
    * Nếu đã đăng nhập, địa chỉ mặc định sẽ được điền sẵn khi thanh toán, có tùy chọn thay đổi.
* **Quản lý Người dùng**:
    * **Đăng ký và Đăng nhập**: Người dùng có thể tạo tài khoản (email, họ tên, địa chỉ giao hàng), đăng nhập và quản lý hồ sơ.
    * **Quản lý Hồ sơ**: Cập nhật thông tin cá nhân, thay đổi/khôi phục mật khẩu, quản lý địa chỉ giao hàng.
* **Duyệt và Tìm kiếm Sản phẩm**:
    * **Danh mục Sản phẩm**: Trang riêng hiển thị sản phẩm với tên, giá, hình ảnh, mô tả ngắn, sử dụng phân trang (cuộn vô hạn).
    * **Chi tiết Sản phẩm**: Thông tin toàn diện bao gồm tên, giá, thương hiệu, các biến thể (yêu cầu tối thiểu hai biến thể mỗi sản phẩm để đạt điểm tối đa), mô tả chi tiết (ít nhất năm dòng), và tối thiểu ba hình ảnh minh họa.
    * **Biến thể Sản phẩm**: Hỗ trợ sản phẩm có nhiều biến thể, mỗi biến thể có theo dõi tồn kho độc lập.
    * **Sắp xếp**: Kết quả có thể được sắp xếp theo ít nhất bốn tiêu chí bao gồm tên (A-Z, Z-A) và giá (tăng dần, giảm dần).
    * **Tìm kiếm và Lọc**: Tìm kiếm sản phẩm và lọc theo ít nhất ba tiêu chí, bao gồm các bộ lọc bắt buộc cho thương hiệu và khoảng giá (tối thiểu/tối đa).
* **Đánh giá và Xếp hạng**:
    * Người dùng có thể để lại bình luận mà không cần đăng nhập.
    * Người dùng phải đăng nhập để xếp hạng sao cho sản phẩm (không cần mua hàng).
    * Khuyến khích cập nhật bình luận và xếp hạng theo thời gian thực bằng WebSockets.
* **Giỏ hàng và Thanh toán**:
    * **Thêm vào Giỏ hàng**: Thêm sản phẩm, cập nhật số lượng, hoặc xóa sản phẩm.
    * **Tóm tắt Giỏ hàng**: Hiển thị tổng giá, thuế và phí vận chuyển.
    * **Quy trình Thanh toán Nhiều bước**: Hướng dẫn người dùng qua các bước nhập thông tin thanh toán, giao hàng và xác nhận đơn hàng.
    * **Thanh toán với tư cách Khách (Guest Checkout)**: Cho phép.
    * **Mã giảm giá**: Áp dụng mã giảm giá cho tổng giá trị đơn hàng. Hiển thị tính hợp lệ và số lần sử dụng còn lại. Chỉ một mã mỗi lần, có thể kết hợp với điểm khách hàng thân thiết/chương trình giảm giá sản phẩm.
* **Quản lý Đơn hàng (Người dùng)**:
    * **Tạo và Xác nhận Đơn hàng**: Hồ sơ đơn hàng được tạo và liên kết với tài khoản người dùng sau khi thanh toán thành công. Màn hình thành công được hiển thị và email xác nhận được gửi.
    * **Theo dõi Đơn hàng**: Theo dõi trạng thái đơn hàng (chờ xử lý, đã xác nhận, đang giao, đã giao) và xem lịch sử trạng thái.
    * **Lịch sử Đơn hàng**: Xem các đơn hàng trước đó với chi tiết như mã đơn, ngày mua, tổng tiền, trạng thái và danh sách sản phẩm.
* **Chương trình Khách hàng Thân thiết**:
    * Tích lũy 10% giá trị tổng đơn hàng thành điểm (ví dụ: đơn 1.000.000 VNĐ = 100 điểm = 100.000 VNĐ).
    * Điểm có thể sử dụng ngay cho đơn hàng tiếp theo không giới hạn.
* **Hỗ trợ Khách hàng qua Chat**:
    * Người dùng có thể gửi tin nhắn văn bản và hình ảnh đến trung tâm hỗ trợ (quản trị viên).
    * Tin nhắn được lưu trữ trong cơ sở dữ liệu.

### Tính năng cho Quản trị viên

* **Bảng điều khiển (Dashboards)**:
    * **Bảng điều khiển Đơn giản**: Tổng quan về hiệu suất cửa hàng: tổng số người dùng, người dùng mới, số lượng đơn hàng, doanh thu, sản phẩm bán chạy nhất (kèm biểu đồ).
    * **Bảng điều khiển Nâng cao**: Thống kê và biểu đồ cho thông tin quan trọng theo các khoảng thời gian cụ thể (hàng năm, hàng quý, hàng tháng, hàng tuần, tùy chỉnh). Theo dõi số lượng đơn hàng đã bán, tổng doanh thu và lợi nhuận tổng thể. Biểu đồ so sánh doanh thu, lợi nhuận, số lượng sản phẩm và loại sản phẩm đã bán, được phân tích theo năm, tháng, quý và tuần.
* **Quản lý Sản phẩm (Quản trị viên)**:
    * Thêm, cập nhật, hoặc xóa sản phẩm, quản lý danh mục và xử lý tồn kho.
    * Định cấu hình phần trăm giảm giá cho sản phẩm cụ thể (tối đa 50%). Sản phẩm giảm giá được hiển thị trong danh mục "Sản phẩm Khuyến mãi".
* **Quản lý Người dùng (Quản trị viên)**:
    * Xem và quản lý tất cả người dùng (cấm, cập nhật thông tin).
* **Quản lý Đơn hàng (Quản trị viên)**:
    * Xem, cập nhật và xử lý đơn hàng (ví dụ: thay đổi trạng thái từ chờ xử lý sang đã xác nhận).
    * Xem danh sách đơn hàng toàn hệ thống (đơn mới nhất trước) với phân trang (khoảng 20 mục/trang).
    * Lọc đơn hàng theo các khoảng thời gian khác nhau (hôm nay, hôm qua, tuần này, tháng này, tùy chỉnh).
    * Xem thông tin chi tiết đơn hàng và thay đổi trạng thái đơn hàng.
* **Quản lý Mã giảm giá (Quản trị viên)**:
    * Xem danh sách mã giảm giá với thông tin chi tiết (thời gian tạo, giá trị mã, số lần đã sử dụng, số lần sử dụng tối đa, danh sách các đơn hàng đã áp dụng mã).
    * Tạo mã giảm giá mới gồm 5 ký tự chữ và số cho các mức giảm giá cố định (10.000 VNĐ, 20.000 VNĐ, 50.000 VNĐ, hoặc 100.000 VNĐ) trên tổng giá trị đơn hàng.
    * Mã không có ngày hết hạn nhưng có giới hạn sử dụng tối đa 10 lần mỗi mã.
* **Hỗ trợ Khách hàng (Quản trị viên)**:
    * Nhận và trả lời tin nhắn của khách hàng (văn bản và hình ảnh). Tất cả tin nhắn được chuyển đến một người dùng quản trị duy nhất.

## Công nghệ sử dụng

* **Frontend**: Flutter, Dart
* **Backend**: Appwrite (Self-hosted hoặc Cloud)
* **Các gói Flutter chính** (từ `pubspec.yaml`):
    * `provider` (Quản lý trạng thái)
    * `appwrite` (Appwrite SDK)
    * `carousel_slider` (Trình chiếu ảnh)
    * `intl` (Quốc tế hóa và định dạng Ngày/Số)
    * `fl_chart` (Biểu đồ cho Bảng điều khiển Admin)
    * `image_picker` (Chọn ảnh cho sản phẩm, avatar, chat)
    * `animated_background` (Nền động)
    * `flutter_localization` (Hỗ trợ bản địa hóa)
    * `shared_preferences` (Lưu trữ cục bộ)
    * `flutter_lints` (Kiểm tra mã)
    * `flutter_launcher_icons` (Tạo biểu tượng ứng dụng)
    * `cupertino_icons` (Biểu tượng kiểu iOS)

## Cấu trúc Dự án

Dự án tuân theo cách tiếp cận ưu tiên tính năng (feature-first) để tổ chức mã nguồn trong thư mục `lib`:

* `lib/main.dart`: Điểm vào chính của ứng dụng, khởi tạo Appwrite và các provider toàn cục.
* `lib/features/`: Chứa các thư mục con cho mỗi tính năng chính của ứng dụng (ví dụ: `auth`, `home`, `products`, `cart`, `checkout`, `orders`, `profile`, `admin`, `support`).
    * Mỗi thư mục tính năng thường chứa:
        * `screens/`: Các màn hình UI cho tính năng.
        * `widgets/`: Các widget có thể tái sử dụng dành riêng cho tính năng.
        * `providers/`: Các provider quản lý trạng thái cho tính năng (nếu đủ phức tạp).
* `lib/models/`: Chứa các lớp mô hình dữ liệu (ví dụ: `appwrite_product.dart`, `appwrite_order.dart`).
* `lib/providers/`: Các provider quản lý trạng thái toàn cục (ví dụ: `auth_provider.dart`, `cart_provider.dart`).
* `lib/services/`: Các lớp dịch vụ để tương tác với API bên ngoài hoặc backend (ví dụ: `appwrite_service.dart`).
* `lib/widgets/`: Các widget chung có thể tái sử dụng trên nhiều tính năng (ví dụ: `common_app_header.dart`).
* `lib/utils/` (Tùy chọn): Các hàm tiện ích, hằng số, v.v.
* `assets/`: Dành cho các tài sản tĩnh như hình ảnh và phông chữ.
    * `assets/images/`: Chứa các hình ảnh của ứng dụng như logo.
    * `fonts/`: Các phông chữ tùy chỉnh như 'Yellowtail'.

## Bắt đầu

Đây là một dự án khởi đầu cho một ứng dụng Flutter.

### Điều kiện tiên quyết

* Flutter SDK: Đảm bảo bạn đã cài đặt Flutter. Tham khảo [hướng dẫn cài đặt Flutter chính thức](https://docs.flutter.dev/get-started/install).
* Dart SDK: Đi kèm với Flutter.
* Một instance Appwrite (tự host hoặc cloud) được cấu hình với Project ID, Database ID, Collections và Buckets cần thiết như đã định nghĩa trong `lib/main.dart`.
    * **Project ID**: `6825fc4a0016e8f531a2`
    * **Database ID**: `tech_store_db`
    * **Collections**: `categories`, `products`, `user_profiles`, `user_carts`, `product_reviews`, `user_addresses`, `orders`, `order_items`, `discount_codes`, `order_status_history`, `support_messages`
    * **Storage Buckets**: `avatars`, `product_images`, `chat_images`
    * **Functions**: `sendOrderConfirmationEmail`, `migrateGuestOrdersToUser`, `awardPointsOnOrderCompletion` (Đảm bảo các function này được tạo và triển khai trên instance Appwrite của bạn).
* Một IDE như Android Studio hoặc VS Code với plugin Flutter và Dart.

### Cài đặt

1.  Sao chép (clone) repository:
    ```bash
    git clone <repository-url>
    cd final_project
    ```
2.  Cài đặt các dependency:
    ```bash
    flutter pub get
    ```
3.  Cấu hình Appwrite:
    * Cập nhật Appwrite endpoint và project ID trong `lib/main.dart` nếu chúng khác với các giá trị mặc định được cung cấp.
    * Đảm bảo instance Appwrite của bạn đã thiết lập các collections, attributes và storage buckets cần thiết theo các hằng số được định nghĩa trong `lib/main.dart` và được sử dụng trong `lib/services/appwrite_service.dart`.

## Chạy Ứng dụng

1.  Đảm bảo một máy ảo đang chạy hoặc một thiết bị đã được kết nối.
2.  Chạy ứng dụng bằng lệnh:
    ```bash
    flutter run
    ```
    Để chạy trên một nền tảng cụ thể:
    ```bash
    flutter run -d <deviceId>
    ```
    (ví dụ: `flutter run -d chrome`, `flutter run -d windows`)

## Triển khai

Ứng dụng phải được triển khai trên các nền tảng sau:
* **Android**: Phiên bản APK (arm64)
* **Windows**: Phiên bản 64-bit (EXE)
* **Web**: Triển khai trên một dịch vụ hosting trực tuyến (ví dụ: Firebase Hosting, GitHub Pages). URL phải được cung cấp.

Việc triển khai phiên bản web thành công sẽ được 0.5 điểm. Phiên bản Windows và APK là bắt buộc nhưng không đóng góp trực tiếp vào điểm số. Nếu không cung cấp các phiên bản triển khai hoạt động được, bài nộp sẽ không được chấm điểm.

## Thông tin Đánh giá

Phần này cung cấp các thông tin cần thiết cho quá trình đánh giá.

### Tài khoản có sẵn để đánh giá

* **Email**: `nguyendangnhuquynh9a66@gmail.com`
* **Mật khẩu**: `nhuquynh`

(Lưu ý: Đây là tài khoản người dùng thông thường. Tài khoản Admin được quản lý riêng trong Appwrite.)

### URL và Thông tin Máy chủ

* **Appwrite Endpoint**: `https://cloud.appwrite.io/v1`
* **Appwrite Project ID**: `6825fc4a0016e8f531a2`
* **URL Web đã triển khai**: `[Vui lòng cập nhật URL sau khi triển khai]`

(Thông tin đăng nhập máy chủ Appwrite không được chia sẻ vì lý do bảo mật. Quá trình đánh giá sẽ tập trung vào chức năng của ứng dụng thông qua các tài khoản được cung cấp và các bản build.)

### Lưu ý về Xây dựng và Chạy Dự án

* Đảm bảo đã cài đặt Flutter và các phụ thuộc theo hướng dẫn ở mục "Bắt đầu".
* Kết nối với instance Appwrite đã được cấu hình đúng với các collection và bucket cần thiết.
* Để chạy trên web, sử dụng: `flutter run -d chrome --web-renderer html` (hoặc `canvaskit` tùy theo sở thích).
* Để build các phiên bản:
    * Android APK: `flutter build apk --release` (Tìm file trong `build/app/outputs/flutter-apk/app-release.apk`)
    * Windows EXE: `flutter build windows --release` (Tìm file trong `build/windows/runner/Release/`)
    * Web: `flutter build web --release` (Các tệp sẽ nằm trong `build/web/`) rồi triển khai thư mục này lên dịch vụ hosting.

## Yêu cầu Chính của Dự án

### Hợp tác Nhóm
Các thành viên trong nhóm phải hợp tác bằng cách sử dụng kiểm soát phiên bản (ví dụ: Git). Bằng chứng về làm việc nhóm, phân chia công việc cân đối, commit sớm và thường xuyên (ít nhất hai commit mỗi thành viên mỗi tuần trong ít nhất một tháng), và hợp tác chủ động phải được chứng minh qua ảnh chụp màn hình GitHub Insights. Làm việc nhóm là bắt buộc; thiếu bằng chứng hợp tác sẽ bị trừ 0.5 điểm.

### UI/UX
Ứng dụng phải có thiết kế rõ ràng, thân thiện với người dùng, điều hướng trực quan, tập trung vào trải nghiệm người dùng, thời gian tải nhanh và tương tác dễ dàng.

### Thiết kế Đáp ứng (Responsive Design)
Ứng dụng (đặc biệt là phiên bản web) phải có thiết kế đáp ứng, thích ứng liền mạch với các thiết bị và kích thước màn hình khác nhau.

### Khả năng Hoạt động Ngoại tuyến (Offline Capability)
Ứng dụng phải hỗ trợ chế độ ngoại tuyến. Người dùng vẫn có thể xem danh sách sản phẩm đã hiển thị trước đó, truy cập thông tin hồ sơ và xem lịch sử mua hàng khi không có kết nối internet. Điều này đòi hỏi tích hợp cả cơ sở dữ liệu trực tuyến và ngoại tuyến (ví dụ: SQL, Hive) để lưu trữ và dự phòng.

## Tính năng Tùy chọn (Bonus)

Việc triển khai các tính năng sau có thể nhận thêm điểm (tối đa 2 điểm):
* **Backend Tùy chỉnh**: Phát triển backend tùy chỉnh (ví dụ: Express.js, NestJS, Spring MVC, ASP.NET) thay vì sử dụng BaaS như Firebase.
* **Kiến trúc Microservices**: Triển khai hệ thống theo kiến trúc microservices (ít nhất ba dịch vụ ngoài frontend/database) với giao tiếp bất đồng bộ (ví dụ: RabbitMQ, Redis).
* **Tính năng liên quan đến AI**: Tích hợp các tính năng như chatbot thông minh gợi ý sản phẩm, tìm kiếm sản phẩm bằng hình ảnh, hoặc Phân tích Cảm xúc (Sentiment Analysis) cho các đánh giá.
* **Tích hợp ElasticSearch**: Sử dụng ElasticSearch để tăng cường tốc độ và hiệu quả tìm kiếm sản phẩm.

Nếu nhóm của bạn triển khai bất kỳ tính năng tùy chọn nào, cần nêu rõ trong biểu mẫu tự đánh giá, tệp README này và video giới thiệu sản phẩm kèm theo bằng chứng cụ thể, thuyết phục.

## Liên hệ

* **By**: Nguyen Dang Nhu Quynh
* **Email**: nguyendangnhuquynh9a66@gmail.com
* **GitHub Repository**: `[Vui lòng cập nhật link GitHub Repo của bạn]`

---
