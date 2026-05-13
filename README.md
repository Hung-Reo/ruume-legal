# Legal Documents

Folder chứa các văn bản pháp lý của RUUME.

## Files

- [`privacy-policy.md`](./privacy-policy.md) — Chính sách bảo mật (Draft v0.1)
- [`terms-of-service.md`](./terms-of-service.md) — Điều khoản sử dụng (Draft v0.1)

## ⚠️ Status

**DRAFT** — chưa qua luật sư review. Phục vụ:

1. UX gate consent checkbox ở signup (#227)
2. App Store / Play Store Privacy nutrition label
3. Baseline compliance Luật BVDLCN 2025 + NĐ 85/2021

**Trước public launch:** bắt buộc luật sư Việt Nam chuyên TMĐT review từng mục, đặc biệt:

- Phần 4 Privacy — chia sẻ dữ liệu (OpenAI, Firebase)
- Phần 6 Privacy — quyền user (deletion timeline, data export)
- Phần 6 TOS — miễn trừ trách nhiệm và giới hạn financial liability
- Điền các `[TBD]` (tên pháp nhân, địa chỉ, email)

---

## Host plan (chưa quyết)

3 option khả dĩ:

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

## Wire URL vào signup

Sau khi host xong, edit [signup.tsx:13-15](../../ruume/app/(auth)/signup.tsx):

```ts
const PRIVACY_URL: string | null = 'https://ruume.vn/privacy';
const TERMS_URL: string | null = 'https://ruume.vn/terms';
```

Và update consent block để Pressable text mở `Linking.openURL(PRIVACY_URL)`.

Tracked: issue #230 (planned).

---

*Last updated: 2026-05-08*
