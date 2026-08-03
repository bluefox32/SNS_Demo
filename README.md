# SNS Builder Demo

A standalone, client-side SNS (Social Networking Service) prototype built with vanilla JavaScript. This demo showcases a complete user authentication and content management system without requiring any backend infrastructure.

[日本語版は下記を参照](#ja)

## Features

- **User Authentication**: Sign up and login functionality with secure password handling
- **Post Management**: Create, view, and search posts with real-time updates
- **Social Interactions**: Like posts and track engagement metrics
- **Persistent Storage**: All data stored in browser LocalStorage for seamless session continuity
- **Responsive Design**: Modern UI that works across desktop and mobile devices
- **Demo Accounts**: Pre-configured test users for quick evaluation

## Quick Start

### Online Demo
Simply open `index.html` in any modern web browser. No installation or server required.

### Local Setup
```bash
git clone <repository-url>
cd sns-builder-demo
# Open index.html in your browser (or use a local server)
python -m http.server 8000  # Python 3
# or
npx http-server  # Node.js
```

Then navigate to `http://localhost:8000`

## Demo Credentials

Test the application with these pre-configured accounts:

| Username | Password | Email |
|----------|----------|-------|
| yamada | password123 | yamada@example.com |
| tanaka | pass456 | tanaka@example.com |

Click "Demo Login" buttons for instant access.

## Architecture

### Data Model
```
users: {
  id, username, email, password, created_at
}

posts: {
  id, user_id, title, content, created_at, updated_at, like_count, comment_count
}

likes: {
  post_id, user_id
}
```

### Technology Stack
- **Frontend**: Vanilla JavaScript (ES6+)
- **Storage**: Browser LocalStorage API
- **Styling**: CSS3 with modern flexbox layout
- **UI Framework**: Custom component-based architecture

### Key Design Decisions

1. **No Backend Required**: All data stored client-side using LocalStorage, making this a true standalone demo
2. **Single HTML File**: Self-contained distribution reduces deployment complexity
3. **Vanilla JS**: No framework dependencies for maximum portability
4. **XSS Protection**: HTML escaping implemented for user-generated content
5. **State Management**: Centralized data management with localStorage sync

## Usage

### Creating a Post
1. Login with any account
2. Fill in the "Create Post" form with title and content
3. Submit to add to the feed

### Searching Posts
- Use the search box to filter posts by title or content
- Real-time filtering with no backend latency

### Liking Posts
- Click the heart icon on any post to like/unlike
- Like count updates immediately

## Browser Compatibility

- Chrome/Edge 60+
- Firefox 55+
- Safari 12+
- Mobile browsers (iOS Safari, Chrome Mobile)

## LocalStorage Schema

```javascript
{
  "currentUser": JSON.stringified user object,
  "allUsers": JSON.stringified array of users,
  "allPosts": JSON.stringified array of posts,
  "allLikes": JSON.stringified array of likes
}
```

## Security Considerations

⚠️ **Demo/Development Only**

This is a prototype demonstration. For production use, implement:
- Backend authentication with secure session tokens
- Password hashing (bcrypt, argon2)
- HTTPS/TLS encryption
- Rate limiting and input validation
- Cross-Site Scripting (XSS) prevention
- Cross-Site Request Forgery (CSRF) tokens

## Future Enhancements

- [ ] Comment functionality
- [ ] User profiles and follow system
- [ ] Rich text editor for posts
- [ ] Image uploads
- [ ] Real-time notifications
- [ ] Backend API integration
- [ ] OAuth authentication

## License

MIT

---

## <a id="ja">SNS Builder デモ（日本語）</a>

Vanilla JavaScriptで構築されたスタンドアロン型SNSプロトタイプ。バックエンド不要の完全クライアント側の実装です。

### 機能

- **ユーザー認証**: サインアップとログイン機能
- **投稿管理**: 投稿の作成・表示・検索
- **ソーシャルインタラクション**: 投稿へのいいね機能
- **データ永続化**: ブラウザのLocalStorageに全データを保存
- **レスポンシブデザイン**: デスクトップ・モバイル対応
- **デモアカウント**: テスト用プリセットアカウント

### クイックスタート

ブラウザで`index.html`を開くだけで実行できます。

### デモ用ログイン情報

| ユーザー名 | パスワード | メール |
|-----------|----------|--------|
| yamada | password123 | yamada@example.com |
| tanaka | pass456 | tanaka@example.com |

### アーキテクチャ

**技術スタック**
- フロントエンド: Vanilla JavaScript (ES6+)
- ストレージ: ブラウザ LocalStorage API
- スタイリング: CSS3 (Flexbox)
- 依存関係: なし（スタンドアロン）

**主な設計ポイント**
- バックエンド不要の完全クライアント実装
- 単一HTMLファイルでの配布
- フレームワーク依存なし（最大の汎用性）
- ユーザー入力のXSS対策済み

### ブラウザ対応

- Chrome/Edge 60以上
- Firefox 55以上
- Safari 12以上
- モバイルブラウザ全般

### 注意事項

⚠️ **デモ・開発用です**

本番環境での使用には以下の実装が必要です：
- バックエンド認証の実装
- パスワードハッシング化（bcrypt等）
- HTTPS/TLS暗号化
- レート制限とバリデーション
- XSS対策の強化
- CSRF トークン

---

**Author**: bluefox32  
**Repository**: [github.com/bluefox32](https://github.com/bluefox32)
