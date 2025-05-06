📂 Cấu trúc dự án trong Git
detective-game/
├── Assets/
│   ├── Art/
│   ├── Audio/
│   ├── Scenes/
│   └── Scripts/
├── ProjectLog/
│   ├── week1.md
│   ├── week2.md
│   ├── roadmap.md
│   └── tasklist.md
├── README.md
├── .gitignore
└── .gitattributes
🌿 Quy tắc nhánh Git
1. Các nhánh chính
    • main: chứa phiên bản ổn định, không commit trực tiếp vào đây
    • dev: nhánh chính để phát triển tính năng, merge feature từ các nhánh con vào
2. Nhánh theo tính năng (feature branch)
Đặt tên theo định dạng: feature/tinh-nang
Ví dụ:
    • feature/move-system
    • feature/npc-dialogue
3. Nhánh theo tuần (tuỳ chọn)
Đặt tên: week1, week2, dùng để gom thay đổi trong tuần đó
🔁 Quy trình làm việc
Mỗi dev:
    1. Pull code mới nhất
git checkout dev
git pull origin dev
    2. Tạo nhánh mới từ dev
git checkout -b feature/tinh-nang
    3. Code → Commit rõ ràng
git add .
git commit -m "[week1][ui] Tạo popup hiển thị clue"
    4. Merge về dev khi xong
git checkout dev
git merge feature/tinh-nang
    5. Push lên remote
git push origin dev
✅ Quy ước commit message
[weekX][tag] Mô tả ngắn gọn
Tag gợi ý:
    • ui: giao diện
    • npc: tương tác nhân vật
    • logic: xử lý gameplay
    • fix: sửa bug
    • test: kiểm thử
    • refactor: chỉnh code không đổi chức năng
🗂 Ghi chú & tiến độ
Sử dụng file trong ProjectLog/:
    • weekX.md: ghi log công việc đã làm, task hoàn thành, note bug
    • roadmap.md: chia milestone lớn trong 1 tháng
    • tasklist.md: danh sách task dạng checklist, cập nhật thường xuyên
Ví dụ nội dung week1.md:
# Week 1 Summary
## ✅ Hoàn thành
- [x] Di chuyển nhân vật cơ bản
- [x] UI popup clue

## 🔧 Đang làm
- [ ] NPC interaction

## 🐞 Bug
- Khi đổi scene, mất đối tượng clue
🔖 Gắn tag và milestone
    • Dùng git tag để đánh dấu các cột mốc như week1-done, v0.1
git tag week1-done
git push origin week1-done
💬 Giao tiếp & phân chia
    • Dùng file tasklist.md để phân chia rõ ai làm gì
    • Ghi tên người nhận task:
- [x] UI Popup – @dev1
- [ ] Dialogue hệ thống – @dev2
💡 Lưu ý 
    • Code luôn commit nhỏ, rõ ràng, dễ merge
    • Không làm nhiều tính năng trong 1 nhánh
    • Check và cập nhật ProjectLog/ mỗi tuần
