---
description: Dream Card Game Guide Contest - XWG Spirit Award Winner
---

# \[ How-to-Play] \[Vietnamese] Guide to buying equipment at good price

### \[ How-to-Play] \[Vietnamese] Guide to buying equipment at good price

Chào tất cả các bạn,\
Bài viết này hướng đến các bạn đã biết các chơi cơ bản của V2, bài viết nhằm mục đích đưa ra thông tin để các bạn có thể giao dịch một cách hiệu quả mà không sợ mình bán rẻ/mua đắt.\
Chúng ta sẽ đi lần lượt từng nội dung dưới dạng hỏi đáp như sau:

#### Q: Equipment hay trang bị kiếm ở đâu?

A: Trang bị kiếm được thông qua 3 phương thức:

* Mở rương thưởng ở các phần (part) với tỉ lệ tăng dần - các phần càng cao tỉ lệ ra trang bị càng cao (VD: ở phần 5, tỉ lệ ra trang bị là 3%). Phân bổ phẩm chất không ghi chi tiết nhưng mình nghĩ cũng sẽ tương đương với phương thức mở hộp ở dưới. Bản thân mình chơi được khoảng 3 tuần rồi nhưng mới chỉ nhận được đồ rare từ rương.
* Mua lại trang bị từ người chơi khác thông qua các chợ NFT như tofunft (fee 5%), mintverse (2%), …
* Mở hộp với giá 20xwg/hộp với tỉ lệ ra đồ và phẩm chất như sau: dust exp - 53,8%, rare - 28%, epic - 13.5%, legend - 3,8%, myth - 0,9%

#### Q: Tôi có trang bị và muốn bán thì thì nên đặt giá như thế nào?

A: Câu hỏi này mình sẽ trả lời dựa trên nguồn equip của các bạn kiếm được

* Nếu là từ mở hộp: đây là khoản earn miễn phí đính kèm, bạn bán giá nào cũng được nhưng nguồn trang bị này rất ít, thường không đáng kể.
* Nếu là mua lại từ người khác: bạn nên treo giá để ít nhất sau khi bán bạn không bị lỗ phí mạng + phí giao dịch trên chợ.
* Nếu là trang bị bạn mở từ hộp 20xwg: câu hỏi này mình sẽ trả lời dựa trên việc giao dịch bằng BNB (vì sàn hỗ trợ giao dịch hiện tại là BNB) và mình cũng có tính sẵn bằng XWG.
* Cấu phần chi phí lên 1 món trang bị khi mở hộp (BOX\_PRICE) bao gồm : phí mở hộp 20xwg, phí mạng khi mở hộp (0.0065+0.00071508)/10 = 0.000721508BNB (0.0065 và 0.00071508 là phí khi mở hộp x10), phí nâng cấp và các món trang bị dùng để nâng cấp.
* Giá trị một trang bị được xác định như thế nào, chúng ta sẽ đi vào ví dụ trực quan (để dễ hiểu chúng ta sẽ chỉ tính giá trị với trang bị chưa nâng cấp):
  * Giả sử chúng ta mở 1000 hộp, ở điều kiện lý tưởng, kết quả chúng ta sẽ thu được: bụi exp - 538, rare - 280, epic - 135, legend - 38, myth - 9
  * Ta xác lập được công thức tính giá trị như sau: d_538 + r_280 + e_135 + l_38 + m\*9 = 1000; với d < r < e < l < m
  * Giả sử giá trị trang bị chỉ dựa trên exp trang bị cung cấp khi dùng làm nguyên liệu, ta sẽ có: d:r:e:l:m = 150:290:600:2150:9600
  * Từ 3 thông tin trên ta xác định được giá trị trang bị khi chưa nâng cấp như sau:\
    \*\* dust\_price = 1000/(538 + 280/150_280 + 600/150_135 + 2150/150_38 + 9600/150_9)_BOX\_PRICE_\
    _\*\* rare\_price = 290/150_dust\_price\
    \*\* epic\_price = 600/150_dust\_price_\
    _\*\* legend\_price = 2150/150_dust\_price\
    \*\* myth\_price = 9600/150\*dust\_price
* Như mình đã trình bày ở trên, chợ tofu giao dịch bằng BNB, mở hộp thì lại tốn XWG nên cần có công thức quy đổi XWG sang BNB để tính giá thành trang bị. Để làm được điều này mình đã tổng hợp tất cả công thức/giá trị vào file google sheet để các bạn tham khảo tại link sau [XWG - Google Sheets 10](https://docs.google.com/spreadsheets/d/1KGSgHY60VDM0AJRi\_43wlljf9UYholw9T5kctGmX\_E0/edit#gid=1766234560). Ở đây giá XWG quy đổi sang BNB được cập nhật mỗi 15 phút.
* Tiếp tục phát triển công thức mình cũng đã có giá trị các món đồ sau nâng cấp (giả sử tất các các món nâng cấp chỉ dùng rare làm nguyên liệu).

#### Q: Tại sao tôi thấy giá các món trên chợ tofu có sự chênh lệch không đồng đều với giá trị trong file google sheet ở trên?

A: Như mình nói ở trên, các công thức và con số dự trên giả định là giá trị chỉ tương đương với exp thu được khi dùng trang bị làm nguyên liệu dẫn đến chênh lệch thực tế như sau:

* Với dust exp chúng ta không thể giao dịch nên chỉ có thể dùng làm nguyên liệu nâng trang bị dẫn đến trang bị đã nâng giá thấp hơn trong file google sheet.
* Với trang bị rare/epic: thanh khoản rất thấp nên giá rất không ổn định, nếu bạn định dùng epic thì nên mở hộp cho đỡ tốn phí mạng + phí chợ
* Trang bị legend gen2 (6\*) trở lên giá thấp hơn khá nhiều so với trong google sheet: những người đã chơi được một thời gian đã có lại và không muốn tiếp tục farm do earn thấp và đồ legend cũng là đồ được nâng cấp phổ biến nhất dẫn đến tình trạng cung lớn hơn cầu làm giá thấp đi
* Trang bị myth giá cao hơn trong file google sheet: do trang bị myth thường được giữ lại sử dụng lâu dài, không có nhiều người muốn bán ra nên giá cao hơn giá bình quân.

**Lưu ý: các giá trị đề cập đến trong bài viết đều là số liệu có được khi thực hiện mở hộp rất nhiều nên nếu các bạn tự mở hộp (số lượng nhỏ) thì kết quả sẽ có sai khác nhất định**

****

Content Creator: namnv89

Link: [https://community.xwg.games/t/how-to-play-vietnamese-guide-to-buying-equipment-at-good-price/361](https://community.xwg.games/t/how-to-play-vietnamese-guide-to-buying-equipment-at-good-price/361)

