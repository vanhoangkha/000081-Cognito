---
title : "Kiểm tra hoạt động"
date: 2024-01-01
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
Chúng ta sẽ thử đăng ký và đăng nhập từ ứng dụng web để kiểm tra hoạt động của API Gateway, Lambda function và User pool
1. Mở bảng điều khiển của [API Gateway](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/apis?region=ap-southeast-1)
- Ấn vào **API Gateway REST API to Lambda**

2. Chọn **Stage** ở menu phía bên trái
- Ấn **staging**
- Ghi lại **InvokeURL**

![UpdateSource](/images/4-test-front-end/4-test-front-end-1.png?featherlight=false&width=90pc)

3. Mở tệp **config.js** trong thư mục source code của ứng dụng - **FCJ-Serverless-Workshop**
- Thay **APP_API_URL** bằng **InvokeURL**

![UpdateSource](/images/4-test-front-end/4-test-front-end-2.png?featherlight=false&width=90pc)

2. Chạy các dòng lệnh dưới đây:
```
yarn build
aws s3 cp build s3://fcj-book-store --recursive
```
3. Mở bảng điều khiển [Amazon S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1)

![WebApp](/images/4-test-front-end/4-test-front-end-3.png?featherlight=false&width=90pc)

4. Ấn chọn bucket **fcj-book-store**

![WebApp](/images/4-test-front-end/4-test-front-end-4.png?featherlight=false&width=90pc)

5. Chọn tab **Properties**

![WebApp](/images/4-test-front-end/4-test-front-end-5.png?featherlight=false&width=90pc)

6. Kéo xuống cuối trang, ấn vào endpoint của web

![WebApp](/images/4-test-front-end/4-test-front-end-6.png?featherlight=false&width=90pc)

7. Ấn **Register** góc bên phải

![WebApp](/images/4-test-front-end/4-test-front-end-7.png?featherlight=false&width=90pc)

8. Nhập thông tin đăng ký email, mật khẩu và nhập lại mật khẩu
- Ấn nút **Register**

![WebApp](/images/4-test-front-end/4-test-front-end-8.png?featherlight=false&width=90pc)

{{% notice note %}}
Đăng ký bằng email mà bạn đang dùng để có thể lấy được code xác thực tài khoản
{{% /notice %}}

9. Bạn sẽ gặp thông báo **Register fail**
- Lỗi do API của chúng ta thiếu **Access-Control-Allow-Headers** trong headers của phản hồi
![RegisError](/images/4-test-front-end/4-test-front-end-error-1.png?featherlight=false&width=90pc)

10. Để giải quyết lỗi này, mở tệp **template.yaml** trong source của tệp **fcj-book-store-sam-ws3.zip**
- Thêm đoạn script sau cho **BookApi**
```
        AllowMethods: "'GET,POST,OPTIONS,DELETE'"
        AllowHeaders: "'content-type'"
        AllowOrigin: "'*'"
```

![RegisError](/images/4-test-front-end/4-test-front-end-error-2.png?featherlight=false&width=90pc)

- Chạy các câu lệnh sau:
```
sam build
sam deploy --guided
```

10. Quay lại màn hình đăng ký và ấn **Register**

11. Trở lại với bảng điều khiển của Amazon Cognito
- Tại tab **Users**, xuất hiên một người dùng nhưng vẫn ở trạng thái **Unconfirmed**

![WebApp](/images/4-test-front-end/4-test-front-end-9.png?featherlight=false&width=90pc)

12. Mở email mà bạn vừa đăng ký tài khoản, lấy mã xác nhận được gửi từ **no-reply@verificationemail.com**
13. Nhập mã xác nhận vào màn hình xác thực
- Ấn **Submit**

![WebApp](/images/4-test-front-end/4-test-front-end-10.png?featherlight=false&width=90pc)

14. Trở lại với bảng điều khiển của Amazon Cognito
- Người dùng đã chuyển sang trạng thái **Confirmed**

![WebApp](/images/4-test-front-end/4-test-front-end-11.png?featherlight=false&width=90pc)

15. Nhập thông tin tài khoản: email, mật khẩu để đăng nhập
- Ấn **Submit**

![WebApp](/images/4-test-front-end/4-test-front-end-13.png?featherlight=false&width=90pc)

16. Sau khi đăng nhập thành công, các tính năng: **Create new book**, **Management**, **Order** xuất hiện cho phép người dùng sử dụng

![WebApp](/images/4-test-front-end/4-test-front-end-14.png?featherlight=false&width=90pc)
