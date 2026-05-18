# Legal Documents

Folder chứa các văn bản pháp lý của RUUME.

## Files

- [`privacy-policy.md`](./privacy-policy.md) — Chính sách bảo mật v1.0
- [`terms-of-service.md`](./terms-of-service.md) — Điều khoản sử dụng v1.0

## Status

**Public v1.0** — bản nội dung dùng cho legal URLs trong app:

1. Consent checkbox ở signup.
2. Settings → Chính sách bảo mật / Điều khoản sử dụng.
3. App Store / Play Store Privacy/Data Safety metadata.
4. GitHub Pages public mirror.

Khi review/chỉnh sửa, ưu tiên kiểm tra các mục này trước khi publish lại GitHub Pages:

- Privacy: phạm vi chia sẻ dữ liệu với Firebase/Google, OpenAI/Gemini, Expo/Apple/Google.
- Privacy: retention thực tế sau account deletion, audit/log retention, data export.
- Terms: subscription/fee/refund nếu RUUME mở trả phí rộng hơn.
- Terms: thông tin đơn vị vận hành nếu sau này có pháp nhân/domain chính thức.

---

## Host plan

URL production hiện đang trỏ tới GitHub Pages public mirror:

- Privacy: `https://hung-reo.github.io/ruume-legal/privacy-policy`
- Terms: `https://hung-reo.github.io/ruume-legal/terms-of-service`

3 option khả dĩ nếu đổi host sau này:

### Option A — GitHub Pages từ docs folder
- **Pros:** miễn phí, không cần infra mới
- **Cons:** repo phải public hoặc enable Pages cho private (paid feature). Hiện repo private.
- **URL pattern:** `https://hung-reo.github.io/ruume-legal/privacy`

### Option B — Vercel standalone (recommend)
- **Pros:** miễn phí, support markdown native, custom domain dễ
- **Cons:** thêm 1 project Vercel
- **URL pattern:** `https://ruume-legal.vercel.app/privacy` hoặc `https://ruume.vn/privacy`
- **Setup:** tạo repo mới `ruume-legal/` chỉ 2 markdown + 1 next.config

### Option C — Tích hợp admin-dashboard (Next.js)
- **Pros:** cùng domain, tái dùng deploy pipeline đã có
- **Cons:** legal docs lộ qua admin domain (không tốt cho UX), tăng coupling
- **URL pattern:** `https://ruume-admin.vercel.app/legal/privacy`

**Recommend:** Option B khi mua domain `ruume.vn`. Trước đó tạm host GitHub Pages từ public mirror repo.

---

## Wire URL trong app

URL hiện đã được wire trong:

- `ruume/app/(auth)/signup.tsx`
- `ruume/app/settings/legal.tsx`

Nếu đổi domain, cập nhật các constants:

```ts
const PRIVACY_URL: string | null = 'https://ruume.vn/privacy';
const TERMS_URL: string | null = 'https://ruume.vn/terms';
```

Consent block đã mở URL qua `Linking.openURL`.

---

*Last updated: 2026-05-18*
