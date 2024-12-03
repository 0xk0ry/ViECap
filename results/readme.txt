Ở cái slide là khi phân biệt giữa hai tấm ảnh ấy thì cái mô hình có lợi nhất từ việc train cả 2 dataset không phải là mô hình caption mà là mô hình ảnh khi dùng cho retrieval.
ý ở đây là khi đưa 2 tấm ảnh khu rừng: 1 màu sáng, 1 màu tối thì mô hình caption khi infer cũng không khác nhau mấy. Cũng theo dạng coco.
Nhưng mà với mô hình ảnh thì nó mới biết phân biệt được là khi query 1 cái bright forest 1 cái gloomy forest thì cho kết quả khác nhau.

Lí do khi mà finetune thì khi m nhìn kết quả inference có thể thấy là việc finetune sẽ giúp mô hình caption generate một cách tốt hơn. Khi mà dùng mô hình pretrain thì bị sai ở phần object detection dẫn đến mô hình caption bị sai. Ví dụ tiêu biểu:
nikolay-bogdanov-belsky_horse-between-birches
jean-david_port-scene
amedee-ozenfant_maternity-1941

Kết lại. Finetune nó sẽ giúp cải thiện được 2 thứ:
Với mô hình ảnh thì khi ta retrieval sẽ cho kết quả chính xác hơn nhờ những tính từ/adjective khi mô tả ảnh.
Với mô hình caption thì khi generate sẽ cho caption chính xác với những vật có trong ảnh hơn, đặc biệt là với những tấm tranh trừu tượng, có đặc tính khác nhiều so với real life (tranh abstract)

Khi mà tao train thì tao quên việc phải tách dataset ra thành các tập train test val. Ở đây là lỗi của tao. Tao không biết mình có thể nói tránh vụ này được không. Nếu thầy có hỏi thì nói là tách ra làm 80 20 thôi.