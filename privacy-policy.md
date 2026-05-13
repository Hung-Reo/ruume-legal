# Chính sách bảo mật RUUME

**Phiên bản:** Draft v0.1
**Hiệu lực:** [TBD — sau khi luật sư review và RUUME launch]
**Cập nhật lần cuối:** 2026-05-08

> ⚠️ **Đây là bản DRAFT phục vụ mục đích UX gate (App Store/Play Store) và baseline compliance.**
> **Bắt buộc tham vấn luật sư Việt Nam chuyên Thương mại điện tử trước khi công khai cho người dùng thật.**
> Tham chiếu pháp lý: Luật Bảo vệ dữ liệu cá nhân 2025 (hiệu lực 01/01/2026), Nghị định 85/2021/NĐ-CP, Luật An ninh mạng 2018.

---

## 1. Giới thiệu

RUUME ("chúng tôi", "ứng dụng") là nền tảng mua bán đồ cũ giữa các thành viên trong cộng đồng gia đình Việt Nam, vận hành bởi [TBD — tên pháp nhân]. Chính sách này mô tả cách chúng tôi thu thập, sử dụng, lưu trữ và bảo vệ dữ liệu cá nhân của bạn khi sử dụng RUUME.

**Bằng việc đăng ký tài khoản và sử dụng RUUME, bạn xác nhận đã đọc, hiểu và đồng ý với toàn bộ Chính sách này.**

---

## 2. Dữ liệu chúng tôi thu thập

### 2.1 Dữ liệu bạn cung cấp trực tiếp

| Loại dữ liệu | Mục đích | Cơ sở pháp lý |
|---|---|---|
| Email, tên người dùng, mật khẩu | Tạo và xác thực tài khoản | Hợp đồng dịch vụ (Điều 17 Luật BVDLCN 2025) |
| Số điện thoại (nếu cung cấp) | Liên hệ giao dịch giữa người mua/bán | Sự đồng ý của bạn |
| Khu vực giao dịch (Hub) | Khớp người mua/bán cùng khu vực | Hợp đồng dịch vụ |
| Hình ảnh, mô tả sản phẩm đăng bán | Hiển thị tin đăng | Hợp đồng dịch vụ |
| Thông tin người bán theo NĐ 85/2021 | Tuân thủ pháp luật về sàn TMĐT | Nghĩa vụ pháp lý |
| Phản hồi/góp ý người dùng | Cải thiện sản phẩm | Sự đồng ý của bạn |

### 2.2 Dữ liệu thu thập tự động

- **Thông tin thiết bị:** loại thiết bị, hệ điều hành, phiên bản ứng dụng — phục vụ debug và bảo mật
- **Log truy cập:** thời gian đăng nhập, địa chỉ IP — phát hiện gian lận, lạm dụng
- **Hành vi sử dụng:** màn hình truy cập, tin đăng đã xem — cải thiện trải nghiệm (Firebase Analytics)
- **Crash/error log:** thông tin kỹ thuật khi ứng dụng lỗi — sửa bug (Firebase Crashlytics)

### 2.3 Dữ liệu chúng tôi KHÔNG thu thập

- ❌ CCCD/CMND, số tài khoản ngân hàng, thông tin sinh trắc học từ ngoài thiết bị
- ❌ Vị trí GPS chính xác (chỉ thu thập khu vực Hub do người dùng tự chọn)
- ❌ Nội dung tin nhắn từ ứng dụng khác, danh bạ điện thoại
- ❌ Dữ liệu sức khỏe, tôn giáo, dân tộc, quan điểm chính trị

---

## 3. Cách chúng tôi sử dụng dữ liệu

- **Vận hành dịch vụ:** xác thực, hiển thị tin đăng, kết nối người mua/bán, thông báo
- **An toàn cộng đồng:** xác minh người bán, phát hiện scam/lừa đảo, xét duyệt thành viên (allowedUsers, trust score)
- **Tuân thủ pháp luật:** lưu thông tin người bán theo NĐ 85/2021, hợp tác cơ quan điều tra khi có yêu cầu hợp pháp
- **AI hỗ trợ (tùy chọn):** quét hình ảnh phát hiện hàng cấm, gợi ý mô tả tin đăng, kiểm duyệt nội dung — sử dụng OpenAI gpt-4o-mini, **không huấn luyện trên dữ liệu của bạn**
- **Phân tích cải thiện:** Firebase Analytics tổng hợp, không tiết lộ danh tính cá nhân

---

## 4. Chia sẻ dữ liệu với bên thứ ba

Chúng tôi **KHÔNG bán** dữ liệu cá nhân của bạn cho bên thứ ba.

Chỉ chia sẻ trong các trường hợp sau:

| Bên thứ ba | Dữ liệu chia sẻ | Mục đích | Đảm bảo |
|---|---|---|---|
| Google Firebase (Auth, Firestore, Storage, Functions, Analytics, Crashlytics) | Toàn bộ dữ liệu vận hành | Lưu trữ và xử lý hạ tầng | Hợp đồng xử lý dữ liệu chuẩn Google, máy chủ khu vực `asia-southeast1` |
| OpenAI | Hình ảnh và mô tả tin đăng (khi user kích hoạt AI scan) | Phân tích nội dung | Theo điều khoản OpenAI Enterprise — không huấn luyện model |
| Người dùng khác trên RUUME | Tên hiển thị, hub, tin đăng, tin nhắn bạn gửi cho họ | Giao dịch P2P | Bạn chủ động chia sẻ |
| Cơ quan nhà nước | Theo yêu cầu hợp pháp bằng văn bản | Tuân thủ pháp luật | Chỉ dữ liệu cụ thể được yêu cầu |

---

## 5. Lưu trữ và bảo mật dữ liệu

- **Vị trí lưu trữ:** Google Cloud `asia-southeast1` (Singapore) — gần Việt Nam, tuân thủ Luật An ninh mạng 2018 về lưu trữ dữ liệu người dùng Việt Nam
- **Mã hóa:** dữ liệu mã hóa khi truyền (HTTPS/TLS) và khi lưu trữ (Google Cloud encryption-at-rest)
- **Mật khẩu:** lưu dạng hash an toàn (Firebase Auth), nhân viên RUUME **không** đọc được mật khẩu của bạn
- **Token nhạy cảm:** lưu trong `expo-secure-store` (Keychain iOS / EncryptedSharedPreferences Android), không lưu AsyncStorage
- **Thời gian lưu trữ:**
  - Dữ liệu tài khoản: trong suốt thời gian bạn sử dụng RUUME
  - Sau khi xóa tài khoản: anonymize trong 30 ngày, xóa hoàn toàn trong 90 ngày
  - Log truy cập: tối đa 12 tháng
  - Tin đăng đã sold/hết hạn: lưu 6 tháng để giải quyết khiếu nại

---

## 6. Quyền của bạn theo Luật BVDLCN 2025

Bạn có các quyền sau với dữ liệu cá nhân của mình:

- **Quyền được biết** — biết rõ dữ liệu nào đang được xử lý
- **Quyền truy cập** — yêu cầu bản sao dữ liệu của mình (data export)
- **Quyền chỉnh sửa** — sửa dữ liệu sai lệch trong Settings → Tài khoản
- **Quyền xóa** — xóa tài khoản và dữ liệu liên quan trong Settings → Xóa tài khoản
- **Quyền hạn chế xử lý** — tạm dừng AI scan, tắt nhận thông báo
- **Quyền phản đối** — không đồng ý với một mục đích xử lý cụ thể
- **Quyền khiếu nại** — gửi khiếu nại tới chúng tôi qua [TBD email] hoặc tới cơ quan nhà nước

**Để thực hiện các quyền trên,** vui lòng dùng tính năng có sẵn trong app hoặc liên hệ [TBD email]. Chúng tôi cam kết phản hồi trong **15 ngày làm việc** theo quy định pháp luật.

---

## 7. Trẻ em dưới 18 tuổi

RUUME **không dành cho người dưới 16 tuổi**. Người dùng từ 16-17 tuổi cần có sự đồng ý của cha mẹ/người giám hộ. Nếu phát hiện tài khoản dưới 16 tuổi, chúng tôi sẽ **xóa ngay lập tức** dữ liệu liên quan.

---

## 8. Cookie và công nghệ tương tự

Ứng dụng RUUME (mobile) **không sử dụng cookie**. Chỉ dùng `AsyncStorage`/`SecureStore` cho session và preferences cục bộ trên thiết bị của bạn.

---

## 9. Thay đổi chính sách

Chúng tôi có thể cập nhật Chính sách này. Khi có thay đổi quan trọng:

- Hiển thị thông báo trong app trước khi áp dụng
- Yêu cầu bạn đồng ý lại nếu thay đổi mở rộng phạm vi xử lý dữ liệu
- Lịch sử phiên bản công khai tại [TBD URL]

---

## 10. Liên hệ

| Mục đích | Liên hệ |
|---|---|
| Hỏi đáp về dữ liệu cá nhân | [TBD email — privacy@ruume.vn] |
| Yêu cầu xóa tài khoản / data export | Settings → Xóa tài khoản, hoặc [TBD email] |
| Khiếu nại / báo cáo vi phạm | [TBD email — support@ruume.vn] |
| Đơn vị chịu trách nhiệm pháp lý | [TBD — tên + địa chỉ pháp nhân] |

---

*Phiên bản: Draft v0.1 — Bản này phục vụ mục đích triển khai UX gate. Toàn bộ nội dung pháp lý cần được luật sư có chuyên môn TMĐT Việt Nam review và phê duyệt trước khi công khai.*
