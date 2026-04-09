# Individual reflection — Nguyễn Đức Dũng (2A202600148)

## 1. Role
- Backend Developer. Phụ trách phần speech-to-text và hỗ trợ các thành viên khác.

## 2. Đóng góp cụ thể
- Dev phần speech-to-text, chạy local cái model Whisper large từ Openai, thêm config để nó chạy tốt hơn với ngữ cảnh tiếng Việt và app gọi xe. Sau đó export thành một api để module khác có thể kết nối được.
- Thử nghiệm các model STT khác, chọn whisper vì miễn phí, đủ mạnh, và có thể chạy local.
- Kết nối STT làm input cho model LLM khác cũng chạy local, tạo thành một pipeline từ voice thành thông tin cuốc xe.
- Hỗ trợ tech cho các thành viên khác (Trí, Bảo), bao gồm hướng dẫn cài đặt hệ thống, hướng dẫn vibe code.
- Kết quả: dù pipeline với whisper large chạy được nhưng lại không đủ nhanh, nhóm sau đó đã chuyển sang giải pháp khác, kết hợp nhiều model.

## 3. Đóng góp khác
- Ghi âm giọng nói để test model

## 4. Điều học được
Trước buổi chiều vẫn nghĩ là dư dả thời gian để ghép mọi module của hệ thống với nhau.
Hệ thống trông có vẻ chạy được, nhưng cần phải nghĩ đến un-happy case, ví dụ như thiếu thông tin. Luôn cần cơ chế error catching.
Để thời gian chết khá nhiều.
Thành viên khác có thể bị kẹt, nhưng họ cũng có thể không nói.
Model lớn có precision cao nhưng chậm, model nhỏ thì nhanh nhưng precision thấp. Cần có cơ chế fallback khác, ví dụ như một model khác, hoặc bằng UX. (Voice to text sai gây khó chịu cho user)

## 5. Nếu làm lại
Thu nhỏ scope hơn. Một số case khó ngoài scope thì nên hardcode.
Cần quan tâm teammate hơn.
Cần ghép các module thành một hệ thống sớm nhất có thể, để tìm xem điểm nghẽn nằm ở đâu. 
Cần log code, tạo file test, error catch đầy đủ.
Tự test các phần khác của teammate để giúp tìm ra lỗi từ sớm.

## 6. AI giúp gì / AI sai gì
- **Giúp:** gợi ý ý tưởng, viết tài liệu, polish đề tài, vibe code. Về tính năng: voice to text, text to json.
- **Sai/mislead:** AI tạo ra tính năng nhưng không fix được lỗi trong tính năng đó; mỗi người vibe code một kiểu trên cùng một file, bị conflict không merge được; voice to text nhận diện sai từ rất nhiều.
