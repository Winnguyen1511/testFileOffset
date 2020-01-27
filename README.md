# testFileOffset
Đây là cách để thêm 1 chuỗi bất kì vào 1 vị trí của 1 file text.
Hàm seekp có nhiệm vụ tìm đến dòng cần tìm. Tham khảo: http://www.cplusplus.com/reference/ostream/ostream/seekp/
Ở đây đối số đầu tiên là Offset, đối số thứ 2 là hướng đi của con trỏ file.
Ví dụ:
_seekp(5, ios_base::beg)
có nghĩa là con trỏ file sẽ đến vị trí thứ 5 tính từ đầu file (begin)
_seekp(-6, ios_base::end)
có nghĩa là con trỏ file sẽ đến vị trí thứ 6 tính từ cuối file trở lên (end)

->Phải biết vị trí cụ thể của từng character (char) trong file để có thể ghi đè lên.
Một khi file đã được ghi thì file sẽ ko tự căn dòng lại đc, ví dụ xóa 1 dòng của file
thì file nó không tự rút lại như Word được.
Tương tự thêm 1 dòng của file thì dòng ở dưới nó cũng không tự xuống dòng được.

->Vậy cách giải quyết nào ? Đấy là lý do tại sao lưu data ngta toàn lưu file kiểu excel hoặc SQL
ko ai lưu kiểu text. Vì text đã ghi rồi thì ko thể nào thêm, bớt, sửa, xóa dễ được.

->Cách đơn giản nhất là: xóa trong program vector đang chạy, thêm hàm updateDatabase(), để mỗi khi gọi ra thì
mình mới ghi vào file lại theo vector. Giống như việc Ctrl + S vậy, khi bấm save thì nó mới lưu, không nhất thiết phải xóa xog 1 câu là lưu ngay. 1 cái nữa là nhớ trước khi exit chương trình thì luôn gọi updataDatabase() để nó ghi vào trước khi thoát, như Word vậy á, khi thoát mà chưa lưu thì nó hỏi là có muốn lưu ko ?

Good luck
