# messenger-chatbot-guideline

## Cấu trúc thư mục
- `config/`: chứa các biến môi trường dùng chung cho cả project. Các biến này được mô tả trong file `default.json` dưới dạng `key:value`.

  Ví dụ ta cần đọc giá trị của `pageAccessToken` thì ta có thể đạt được bằng cách gọi: `config('pageAccessToken')`; trong đó `config` thực chất là một thư viện giúp đọc file `config/default.json` - sẽ giới thiệu về thư viện trong mục `node_modules` dưới đây.
- `node_modules/`: là folder chứa các thư viện (libs/dependencies) hỗ trợ nodejs. Các thư viện được quản lý bởi `npm` ([node package management](https://www.npmjs.com/)).
  
  npm hỗ trợ việc cài đặt, gỡ và quản lý các thư viện mà ta cần sử dụng trong project. Các mô tả về project đều nằm trong file `package.json` mà ta có thể tạo ra bằng lệnh `npm init` từ Terminal (hoặc có thể tạo tay).
  
  `package.json` cũng ở dạng json (key:value). Các thư viện nodejs được khai báo trong `dependencies` của file này. Dưới đây là một ví dụ:
  ```json
  // package.json
  {
    "name": "messenger-get-started", 
    "version": "1.0.0", 
    "description": "Get started example for Messenger Platform",
    "main": "app.js",
    "scripts": {
      "start": "node app.js",
      "lint": "jshint --exclude node_modules .",
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "repository": {
      "type": "git",
      "url": "https://github.com/fbsamples/messenger-platform-samples.git"
    },
    "author": "Facebook",
    "license": "ISC",
    "dependencies": {
      "body-parser": "^1.15.0",
      "config": "^1.20.4",
      "ejs": "^2.4.2",
      "express": "^4.13.4",
      "request": "^2.72.0"
    },
    "engines": {
      "node": "~4.1.2"
    }
  }
  ```
- `public/`: chứa các content static để gửi đi (ảnh, video, audio, html files...)
- `views/`: views engine phục vụ xem trên trình duyệt. Không cần quan tâm file này.
- `app.js`: file chính của cả chương trình. Trong code mẫu của facebook, họ để chung code ở mỗi một file này, còn khi chúng ta làm product thật thì hiển nhiên phải cấu trúc lại thư mục, không thể để code ở chung một file được.
- `package.json`: như đã giới thiệu, là file mô tả project (tựa như pom.xml của maven). File này được đọc và ghi bởi `npm`
