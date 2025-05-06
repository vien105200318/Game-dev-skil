<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DEV-workfollow</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f9;
            margin: 20px;
            color: #333;
        }
        h1, h2, h3 {
            color: #444;
        }
        ul {
            margin-left: 20px;
        }
        .folder-structure {
            font-family: monospace;
            background-color: #f0f0f0;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 20px;
            white-space: pre-wrap;
        }
        .code-block {
            background-color: #e9e9e9;
            padding: 10px;
            border-radius: 5px;
            font-family: monospace;
            white-space: pre-wrap;
            word-wrap: break-word;
            margin-bottom: 20px;
        }
        .task-list input {
            margin-right: 10px;
        }
        .section-header {
            background-color: #d9f8d9;
            padding: 10px;
            border-radius: 5px;
            margin-top: 20px;
        }
        .highlight {
            color: #1e7e34;
        }
        ol {
            padding-left: 20px;
        }
        code {
            background-color: #f5f5f5;
            padding: 2px 6px;
            border-radius: 4px;
        }
    </style>
</head>
<body>

<h1>📂 <strong>Cấu trúc Dự án trong Git</strong></h1>

<div class="folder-structure">
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
</div>

<h2>🌿 <strong>Quy tắc Nhánh Git</strong></h2>

<h3>1. Các nhánh chính</h3>
<ul>
    <li><strong>main:</strong> Chứa phiên bản ổn định, không commit trực tiếp vào đây.</li>
    <li><strong>dev:</strong> Nhánh chính để phát triển tính năng. Merge các nhánh con (feature) vào nhánh này.</li>
</ul>

<h3>2. Nhánh theo tính năng (feature branch)</h3>
<ul>
    <li>Đặt tên theo định dạng: <code>feature/tinh-nang</code></li>
    <li>Ví dụ:
        <ul>
            <li><code>feature/move-system</code></li>
            <li><code>feature/npc-dialogue</code></li>
        </ul>
    </li>
</ul>

<h3>3. Nhánh theo tuần (tuỳ chọn)</h3>
<ul>
    <li>Đặt tên: <code>week1</code>, <code>week2</code>, dùng để gom thay đổi trong tuần đó.</li>
</ul>

<h2>🔁 <strong>Quy trình làm việc</strong></h2>

<h3>Mỗi dev làm theo các bước sau:</h3>

<ol>
    <li><strong>Pull code mới nhất</strong><br><code>git checkout dev</code><br><code>git pull origin dev</code></li>
    <li><strong>Tạo nhánh mới từ dev</strong><br><code>git checkout -b feature/tinh-nang</code></li>
    <li><strong>Code → Commit rõ ràng</strong><br><code>git add .</code><br><code>git commit -m "[week1][ui] Tạo popup hiển thị clue"</code></li>
    <li><strong>Merge về dev khi xong</strong><br><code>git checkout dev</code><br><code>git merge feature/tinh-nang</code></li>
    <li><strong>Push lên remote</strong><br><code>git push origin dev</code></li>
</ol>

<h2>✅ <strong>Quy ước Commit Message</strong></h2>

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

<h2>🗂 <strong>Ghi chú & Tiến độ</strong></h2>

<h3>Sử dụng file trong <code>ProjectLog/</code>:</h3>
<ul>
    <li><strong>weekX.md</strong>: Ghi log công việc đã làm, task hoàn thành, note bug</li>
    <li><strong>roadmap.md</strong>: Chia milestone lớn trong 1 tháng</li>
    <li><strong>tasklist.md</strong>: Danh sách task dạng checklist, cập nhật thường xuyên</li>
</ul>

<h3>Ví dụ nội dung <code>week1.md</code>:</h3>

<div class="code-block">
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
</div>

<h2>🔖 <strong>Gắn Tag và Milestone</strong></h2>

<p>Dùng git tag để đánh dấu các cột mốc như <code>week1-done</code>, <code>v0.1</code></p>
<div class="code-block">
<pre>
git tag week1-done
git push origin week1-done
</pre>
</div>

<h2>💬 <strong>Giao tiếp & Phân chia</strong></h2>

<ul>
    <li><strong>Sử dụng file <code>tasklist.md</code> để phân chia rõ ai làm gì.</strong></li>
    <li>Ghi tên người nhận task:
        <ul>
            <li><input type="checkbox" checked> UI Popup – @dev1</li>
            <li><input type="checkbox"> Dialogue hệ thống – @dev2</li>
        </ul>
    </li>
</ul>

<h2>💡 <strong>Gợi ý</strong></h2>
<ul>
    <li>Code luôn commit nhỏ, rõ ràng, dễ merge.</li>
    <li>Không làm nhiều tính năng trong 1 nhánh.</li>
    <li>Check và cập nhật <code>ProjectLog/</code> mỗi tuần.</li>
</ul>

</body>
</html>
