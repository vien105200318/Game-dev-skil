# 📂 **Cấu trúc Dự án trong Git**

<pre>
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
</pre>

---

# 🌿 **Quy tắc Nhánh Git**

## 1. **Các nhánh chính**

<ul>
    <li><strong>main:</strong> Chứa phiên bản ổn định. Không commit trực tiếp vào đây.</li>
    <li><strong>dev:</strong> Nhánh chính để phát triển tính năng. Merge các nhánh con (feature) vào nhánh này.</li>
</ul>

## 2. Nhánh theo tính năng (feature branch)

<p>Đặt tên theo định dạng: <code>feature/tinh-nang</code></p>

<ul>
    <li>Ví dụ:
        <ul>
            <li><code>feature/move-system</code></li>
            <li><code>feature/npc-dialogue</code></li>
        </ul>
    </li>
</ul>

---

# 🔁 **Quy trình làm việc**

### **Mỗi dev làm theo các bước sau:**

<ol>
    <li><strong>Pull code mới nhất</strong><br><code>git checkout dev</code><br><code>git pull origin dev</code></li>
    <li><strong>Tạo nhánh mới từ dev</strong><br><code>git checkout -b feature/tinh-nang</code></li>
    <li><strong>Code → Commit rõ ràng</strong><br><code>git add .</code><br><code>git commit -m "[week1][ui] Tạo popup hiển thị clue"</code></li>
    <li><strong>Merge về dev khi xong</strong><br><code>git checkout dev</code><br><code>git merge feature/tinh-nang</code></li>
    <li><strong>Push lên remote</strong><br><code>git push origin dev</code></li>
</ol>

# ✅ **Quy ước Commit Message**

<p>Format commit: <code>[weekX][tag] Mô tả ngắn gọn</code></p>

<h3>Các tag gợi ý:</h3>
<ul>
    <li><strong>ui:</strong> Giao diện</li>
    <li><strong>npc:</strong> Tương tác nhân vật</li>
    <li><strong>logic:</strong> Xử lý gameplay</li>
    <li><strong>fix:</strong> Sửa bug</li>
    <li><strong>test:</strong> Kiểm thử</li>
    <li><strong>refactor:</strong> Chỉnh code không đổi chức năng</li>
</ul>

# 🗂 **Ghi chú & Tiến độ**

<p>Sử dụng file trong <code>ProjectLog/</code>:</p>
<ul>
    <li><strong>weekX.md</strong>: Ghi log công việc đã làm, task hoàn thành, note bug</li>
    <li><strong>roadmap.md</strong>: Chia milestone lớn trong 1 tháng</li>
    <li><strong>tasklist.md</strong>: Danh sách task dạng checklist, cập nhật thường xuyên</li>
</ul>

<h3>Ví dụ nội dung <code>week1.md</code>:</h3>

<pre>
# Week 1 Summary

## ✅ Hoàn thành
- [x] Di chuyển nhân vật cơ bản
- [x] UI popup clue

## 🔧 Đang làm
- [ ] NPC interaction

## 🐞 Bug
- Khi đổi scene, mất đối tượng clue
</pre>

---

# 🔖 **Gắn Tag và Milestone**

<p>Dùng git tag để đánh dấu các cột mốc như <code>week1-done</code>, <code>v0.1</code></p>
<pre>
git tag week1-done
git push origin week1-done
</pre>

# 💬 **Giao tiếp & Phân chia**

<ul>
    <li><strong>Sử dụng file <code>tasklist.md</code> để phân chia rõ ai làm gì.</strong></li>
    <li>Ghi tên người nhận task:
        <ul>
            <li><input type="checkbox" checked> UI Popup – @dev1</li>
            <li><input type="checkbox"> Dialogue hệ thống – @dev2</li>
        </ul>
    </li>
</ul>

# 💡 **Gợi ý**

<ul>
    <li>Code luôn commit nhỏ, rõ ràng, dễ merge.</li>
    <li>Không làm nhiều tính năng trong 1 nhánh.</li>
    <li>Check và cập nhật <code>ProjectLog/</code> mỗi tuần.</li>
</ul>
