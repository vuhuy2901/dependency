# PTIT LTM Web Service Client Dependency Template

## 1. File nội dung
- `dependency.txt` & `dependencies.txt`: Đoạn cấu hình `<dependencies>` và `<build>` dán vào file `pom.xml` của Maven project.
- `pom.xml`: Mẫu file `pom.xml` hoàn chỉnh chạy với Java 17+.

## 2. Lưu ý khi đi thi
1. **Kiểm tra mạng phòng thi**:
   - Máy thi có truy cập được GitHub và Maven Central (`repo.maven.apache.org`) hay không.
   - Nếu phòng thi chặn mạng ngoài (chỉ cho vào mạng LAN / server đề bài `36.50.135.242`), Maven sẽ không tải được thư viện về nếu máy chưa có sẵn cache trong thư mục `.m2`.
2. **Cách 1 - Dự phòng dùng Ant Project (Không cần mạng tải thư viện)**:
   - Tạo Java with Ant -> Java Application.
   - Chuột phải Project -> New -> Other... -> Web Services -> Web Service Client.
   - Dán URL WSDL (ví dụ: `http://36.50.135.242:2221/CharacterService?wsdl`) -> Finish.
3. **Cách 2 - Dùng Maven Project**:
   - Tạo Java with Maven -> Java Application.
   - Dán nội dung `<dependencies>` và `<build>` từ `dependency.txt` vào `pom.xml`.
   - Chỉnh lại tên Service trong `<wsdlUrl>` tương ứng đề bài (`CharacterService`, `DataService`, `ObjectService`,...).
   - Nhấn **Clean and Build** để plugin sinh code client vào package `client`.
