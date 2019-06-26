Tài liệu này được dịch lại sang Tiếng Việt từ gautamkrishnar/github-pages-gallery cho các bạn dễ hiểu  
Bạn có thể đọc bản Tiếng Anh ở [đây](https://github.com/gautamkrishnar/github-pages-gallery)  
Dịch bởi Dương Tùng Anh
# Github Pages Gallery
Host một thư viện ảnh/video trên Github pages hoàn toàn miễn phí một cách dễ dàng sử dụng Thumbsup & Travis CI
### Tại sao dự án này được tạo ra?

Dự án này chứa mã nguồn mở cho newbies để ai cũng có thể deploy một thư viện ảnh/video của riêng mình trên Github Pages, **Không cần phải biết lập trình cũng làm được ha**. Vì Github pages là một nền tảng hosting miễn phí được cung cấp bởi Github dùng để host những trang web dạng tĩnh, nó cho bạn một dung lượng sử dụng cũng kha khá. Vì vậy nó là một sự lựa chọn hoàn hảo cho những người nhiếp ảnh gia để showcase những tác phẩm họ chụp được. Travis-CI là một nền tảng CI & CD cho phép build những dự án mã nguồn mở không giới hạn dung lượng. Kết hợp những sức mạnh của GitHub Pages với lại Travis CI sẽ là một giải pháp không mất tí tiền nào để có một thư viện online.

### Cách sử dụng
Hãy làm theo những bước dưới đây để có một thư viện online cho riêng mình. Bạn sẽ chỉ sử dụng giao diện web của GitHub để làm mọi thứ. 
:wink: Không phải đau đầu với CLIs:
1. Đăng ký một tài khoản Github và kiểm tra email: https://github.com/join
2. Fork cái repo này:
![fork](https://user-images.githubusercontent.com/8397274/47970004-a0fd9880-e0a5-11e8-8f46-966e21d39c87.gif)
3. Chỉnh sửa file [config.json](config.json) bằng cách nhấn vào cái nút Edit (ở trong repo đã fork được):

```
{
  "input": "./gallery",
  "output": "./build_output",
  "title": "Photo Gallery", // Đặt cái tên thư viện của bạn ở đây
  "sort-albums-by": "title",
  "sort-media-by": "filename",
  "download-photos": "copy",
  "cleanup": true,
  "theme": "cards", // Theme mà bạn muốn chọn
  "theme-style": "./custom.css",
  "footer": "Copyright Text", // Tuỳ chỉnh cái dòng chữ ở chân trang
  "usage-stats": false
}
```
Bạn có thể chọn những cái theme ở dưới đây để tuỳ chỉnh cho cái key:
* `mosaic` - https://thumbsup.github.io/demos/themes/mosaic/
* `cards` - https://thumbsup.github.io/demos/themes/cards/
* `classic` - https://thumbsup.github.io/demos/themes/classic/ 

Bạn có thể tìm hiểu thêm về cách tuỳ chỉnh các thiết lập ở đây: https://thumbsup.github.io/docs/3-configuration/usage/. Click vào commit changes để đăng tải lên những thay đổi.

4. Tạo một tài khoản mới tại https://travis-ci.org. Cho phép tất cả các quyền của tài khoản Github khi bạn đăng ký.
5. Sau khi đăng nhập xong gạt cái nút này để bật repo:
![travis](https://user-images.githubusercontent.com/8397274/47970260-33ec0200-e0a9-11e8-99e0-c94fe41034cf.gif)
6. Vào trang cho dự án bằng cách bấm vô cái tên dự án:
![project](https://user-images.githubusercontent.com/8397274/47970299-8e855e00-e0a9-11e8-9218-64cf97402776.png)
7. Bấm vào More > Settings:
![settings](https://user-images.githubusercontent.com/8397274/47970319-da380780-e0a9-11e8-837a-4a734cceba7a.png)
8. Kéo xuống phần "Environment Variables". Tạo một cái environment variable tên là **GITHUB_TOKEN**:
![token](https://user-images.githubusercontent.com/8397274/47970352-43b81600-e0aa-11e8-93bc-8590208b74a7.png)
9. Để chỉnh value của cái variable, mở một tab mới và lấy một cái token từ Github bằng cách truy cập: https://github.com/settings/tokens.
10. Bấm vô **Generate New Token**. Gõ bất kỳ cái tên mà bạn muốn. Đảm báo rằng bạn chọn tất cả các quyền cho repo 
đối với token: 
![authtoken](https://user-images.githubusercontent.com/8397274/47970413-f5efdd80-e0aa-11e8-96b0-50199855b9b3.png)
11. Kéo xuống và bấm vào nút Generate token. Copy cái token bạn thấy trên trang:
12. Paste cái token vào dòng environment variable trong Travis CI:
![toekenenv](https://user-images.githubusercontent.com/8397274/47970465-b1b10d00-e0ab-11e8-8873-abf122708773.png)
13. Bấm vào nút Add. OK bạn xong xuôi rồi đấy.

#### Thêm một album vào thư viện
1. Vào cái thư mục tên là gallery ở cái repo mà bạn đã fork về.
2. Bấm vào Create a new file.
3. Gõ tên với dạng Tên Album/.gitkeep ở cái hộp.
4. Bấm vô Commit Changes ở bên dưới.

![newfolder](https://media.giphy.com/media/455paOHOAWr4KWNOtg/giphy.gif)

#### Thêm video và ảnh
1. Vào thư mục gallery. Mở tiếp bất kỳ cái album nếu có.
2. Bấm vào Upload files
3. Chọn ảnh hoặc video bạn muốn. Tải lên xong thì bấm Commit Changes.

![selectmedia](https://media.giphy.com/media/2uIfenjYx5anbQOEAo/giphy.gif)

#### Tìm URL cho website của bạn
Nếu bạn hoàn thành đúng các bước trên thì website của bạn đã chạy rồi đấy. Bạn có thể check trạng thái build của website trên Travis CI. Nếu bạn thấy một cái badge có tên build passing như thế này thì chúc mừng, site của bạn đã chạy:

![travis](https://user-images.githubusercontent.com/8397274/48001817-a99ab100-e12f-11e8-915a-f7a787eb6b0b.png)

Nếu không thấy thì hãy chờ thêm tầm 2 phút ha để Travis nó build trang của bạn. Free mà nên hơi lâu =))) Badge nó hiện màu đỏ build failed thì ố ồ bạn gặp bug rồi đó!! Hãy rà soát lại xem bạn đã làm sai ở đâu, cố lên!!! =)))
#### Chọn branch gh-pages làm nguồn cho Github pages
Giờ thì quay lại cái trang repo đã fork. Click vào tab Settings. Kéo xuống phần GitHub pages. Kiểm tra lại và chắc chắn rằng branch tên **gh-pages** được lựa chọn để làm **Nguồn** cho GitHub pages. 

Giờ thì bạn sẽ thấy cái URL của trang web:
![url](https://user-images.githubusercontent.com/8397274/48008065-f639b880-e13e-11e8-9f8e-72d27ad7cc30.png)

Bạn có thể đổi tên cái repo nếu bạn cần một cái link đẹp như kiểu `/gallery'. Bạn cũng có thể thêm một cái tên miền tuỳ chỉnh cho trang của bạn: https://help.github.com/articles/adding-or-removing-a-custom-domain-for-your-github-pages-site/

## Những giới hạn
* [Điều khoản pháp lý](https://help.github.com/articles/github-terms-of-service/) của GitHub Pages có nói:
> If your bandwidth usage significantly exceeds the average bandwidth usage (as determined solely by GitHub) of other GitHub customers, we reserve the right to immediately disable your account or throttle your file hosting until you can reduce your bandwidth consumption.  
Nghĩa là: Nếu băng thông của bạn dùng quá lớn hơn mức trung bình (đã được GitHub đề ra) hoặc những khách hàng GitHub khác, chúng tôi có quyền ngay lập tức khoá tài khoản của bạn hoặc làm chậm server hosting cái file của bạn cho đến khi bạn giảm mức băng thông.

Điều này là rất dễ xảy ra. Bạn có thể dùng [Netlify](https://www.netlify.com/) trong cái branch gh-pages để host trang web của bạn, nếu bạn muốn một băng thông không giới hạn. 

* Giới hạn kích cỡ tệp tin (100 MB) & Giới hạn kích cỡ repo (1 GB): Github giới hạn dung lượng mỗi file dưới 100MB.
Với nhiều người thì đây là một dung lượng khá ít vì nhỡ bạn có một cái video trên 100MB thì không thể up lên được. Và nó cũng giới hạn kích cỡ repo chỉ dưới 1GB. Truy cập https://help.github.com/articles/what-is-my-disk-quota/ để biết thêm thông tin.


## Công cụ đã sử dụng
* [Travis CI](https://travis-ci.org/) một nền tảng Continuous Development miễn phí.
* [Thumbsup](https://thumbsup.github.io/) một công cụ giúp bạn tự động tạo một trang thư viện ảnh tĩnh.
* [GithHub Pages]() để hosting các file.

## Đóng góp
Bạn có thể tự do thay đổi và PR.
