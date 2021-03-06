# Chương 2: Cài đặt Docker Desktop

Bài này chỉ hướng dẫn cài đặt cho Hệ điều hành Windows. Các hệ điều hành khác có thể tham khảo thêm tại [Docker Desktop](https://docs.docker.com/desktop/).

## Table of Contents
- [1. Docker Desktop là gì?](#1-docker-desktop-là-gì)
- [2. Một số tính năng chính của Docker Desktop](#2-một-số-tính-năng-chính-của-docker-desktop)
- [3. Tải và cài đặt Docker Desktop](#3-tải-và-cài-đặt-docker-desktop)
  - [Tải Docker Desktop](#tải-docker-desktop)
  - [Cài đặt Docker Desktop](#cài-đặt-docker-desktop)
- [4. Tạo tài khoản trên Docker Hub](#4-tạo-tài-khoản-trên-docker-hub)
  - [Docker Hub là gì?](#docker-hub-là-gì)
  - [Tạo tài khoản trên Docker Hub](#tạo-tài-khoản-trên-docker-hub)
  - [Đăng nhập tài khoản Docker Hub trên Docker Desktop](#đăng-nhập-tài-khoản-docker-hub-trên-docker-desktop)
- [Reference](#reference)
- [License & Copyright](#license--copyright)

## 1. Docker Desktop là gì?
Docker Desktop là một ứng dụng cho phép bạn xây dựng và chia sẻ các ứng dụng thông qua các thùng chứa (Container)

Docker Desktop bao gồm [Docker Engine](https://docs.docker.com/engine/), Docker CLI client, [Docker Compose](https://docs.docker.com/compose/), [Docker Content Trust](https://docs.docker.com/engine/security/trust/), [Kubernetes](https://github.com/kubernetes/kubernetes/), và [Credential Helper](https://github.com/docker/docker-credential-helpers/)

Docker Desktop hoạt động với sự lựa chọn của bạn về các công cụ và ngôn ngữ phát triển, đồng thời cung cấp cho bạn quyền được truy cập vào một thư viện rộng lớn gồm các images và templates trong [Docker Hub](https://hub.docker.com/)

## 2. Một số tính năng chính của Docker Desktop
- Khả năng chứa và chia sẻ bất kì ứng dụng nào trên bất kì nền tảng đám mây nào, bằng nhiều ngôn ngữ và frameworks
- Dễ dàng cài đặt và thiết lập một môi trường phát triển Docker hoàn chỉnh
- Bao gồm phiên bản mới nhất của Kubernetes
- Cập nhật tự động để giúp bạn luôn cập nhật và bảo mật
- Trên Windows, khả năng chuyển đổi giữa các môi trường Linux và Windows Server để xây dựng các ứng dụng
- Hiệu suất nhanh và đáng tin cậy với Windows Hyper-V virtualization
- Khả năng làm việc trên Linux thông qua WSL 2 trên Windows
- Chứa lượng lớn code và dữ liệu, bao gồm thông báo thay đổi tệp và dễ dàng truy cập vào các vùng chứa đang chạy trên localhost network
- In-container development and debugging với các IDE được hỗ trợ

## 3. Tải và cài đặt Docker Desktop

### Tải Docker Desktop
Để tải Docker Destop, truy cập đường dẫn https://docs.docker.com/desktop/windows/install/, tìm và cài đặt Docker Desktop phù hợp với hệ điều hành của máy bạn. Bài hướng dẫn dưới đây dành cho hệ điều hành Windows

### Cài đặt Docker Desktop
- Tìm và chạy file `Docker Desktop Installer.exe` đã tải về ở trên
- Màn hình hiện các thiết lập cho việc cài đặt, **nhấn chọn tất cả**, sau đó chọn **OK** để bắt đầu quá trình cài đặt
  ![Configuration](./imgs/chapter2/1.png)
- Lúc này Docker Desktop sẽ tự động được cài đặt vào máy của bạn
  ![Setup](./imgs/chapter2/2.png)
- Sau khi quá trình cài đặt hoàn tất, Docker Desktop sẽ yêu cầu restart máy của bạn, chọn **Close and restart**
  ![Setup](./imgs/chapter2/3.png)
- Sau khi máy tính được khởi động, Docker Desktop sẽ tự động được mở trở lại, và bạn cần chấp nhận các quy định của Docker Desktop. Nhấn chọn vào **I accept the terms" và sau đó chọn nút **Accept**
  ![Setup](./imgs/chapter2/4.png)
- Tuy nhiên lúc này sẽ xuất hiện lỗi do máy bạn chưa được cài đặt [WSL2](https://docs.microsoft.com/en-us/windows/wsl/about). Truy cập đường dẫn https://aka.ms/wsl2kernel để thực hiện cài đặt
  ![Setup](./imgs/chapter2/5.png)
- Bấm vào **WSL2 Linux kernel update package for x64 machines** để tải WSL2 về máy
  ![Setup](./imgs/chapter2/6.png)
- Sau khi đã tải về máy, tìm và chạy file `wsl_update_x64.msi` đề cài đặt, nhấn **Next** để tiếp tục
  ![Setup](./imgs/chapter2/7.png)
- Sau khi hoàn tất cài đặt WSL2, nhấn **Finish** để hoàn tất
  ![Setup](./imgs/chapter2/8.png)
- Sau khi hoàn tất cài đặt WSL2 ở bước trên, thực hiện khởi động và mở lại Docker Desktop, màn hình hiển thị như sau
  ![Setup](./imgs/chapter2/9.png)
- Nếu quá trình khởi động Docker Desktop vẫn chưa thành công, bạn hãy chuột phải vào icon Docker Desktop dưới thanh taskbar, chọn **Quit Docker Desktop**, và sau đó mở lại Docker Desktop là công
  ![Setup](./imgs/chapter2/10.png)

Tuy nhiên Docker Desktop là một chương trình chạy làm hao tốn rất nhiều tài nguyên của máy bạn, vì thế khi khởi động máy tính, nó sẽ được mở ngầm cùng lúc với việc khởi động Windows, điều này sẽ làm máy bạn khởi động chậm. Nên mình khuyên là hãy thực hiện những bước sau để Docker Desktop không khởi động cùng lúc với Windows của máy gây chậm máy
- Đầu tiên mở Task Manager của máy lên
- Chọn phần **Startup**
  ![Setup](./imgs/chapter2/12.png)
- Nhấn chuột phải vào mục **Status** của Docker Desktop, tại **Enable** và thay đổi thành **Disable**
  ![Setup](./imgs/chapter2/13.png)
  
Như vậy là bạn đã hoàn tất quá trình tải, cài đặt Docker Desktop trên hệ điều hành Windows

## 4. Tạo tài khoản trên Docker Hub
### Docker Hub là gì?
- Docker Hub là một dịch vụ được cung cấp bởi Docker cho việc tìm kiếm và chia sẻ container images với nhóm của bạn.
- Đây là "kho" lưu trữ container images lớn nhất trên thế giới với một lượng lớn tài nguyên bao gồm cộng đồng các nhà phát triển container, các dự án mã nguồn mở và các nhà cung cấp phần mềm độc lập (independent software vendors - ISV) xây dựng và phân phối mã của họ trong các container
- Người dùng có quyền truy cập các kho công khai miễn phí trên Docker Hub cho việc lưu trữ và chia sẻ images

### Tạo tài khoản trên Docker Hub
- Truy cập đường dẫn đến Docker Hub: https://hub.docker.com/
- Chọn biểu tượng Sign Up ở góc phải màn hình
  ![Docker Hub](./imgs/chapter2/14.png)
- Tạo tài khoản trên Docker Hub với **tên tài khoản, email, và mật khẩu**. Sau đó nhấn chọn đồng ý vào các điều khoản của Docker Hub, và cuối cùng là nhấn **Sign Up** để hoàn tất đăng kí
  ![Docker Hub](./imgs/chapter2/15.png)
- Sau đó Docker Hub sẽ chuyển bạn đến trang Log In, thực hiện đăng nhập với tài khoản và mật khẩu đã đăng kí ở bước trên, chọn **Continue** để hoàn tất các bước

  ![Docker Hub](./imgs/chapter2/16.png) ![Docker Hub](./imgs/chapter2/17.png)
- Docker Hub yêu cầu bạn lựa chọn một gói hoạt động trên Docker Hub với từng mức hỗ trợ làm việc cụ thể, ở đây chúng ta sẽ chọn gói **Personal** và chọn **Continue with Free** để xác nhận
  ![Docker Hub](./imgs/chapter2/18.png)
- Bước cuối cùng của việc đăng kí tài khoản trên Docker Hub là xác thực tài khoản email
  ![Docker Hub](./imgs/chapter2/19.png)  

### Đăng nhập tài khoản Docker Hub trên Docker Desktop
- Mở Docker Desktop trên máy tính của bạn
- Tại góc phải màn hình, tìm và nhấn chọn Sign In
  ![Sign In](./imgs/chapter2/20.png)
- Đăng nhập tài khoản Docker Hub đã đăng kí ở bước trên
  ![Sign In](./imgs/chapter2/21.png)  

## Reference
- [Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/)
- [Docker Desktop overview](https://docs.docker.com/desktop/)
- [Docker Hub Quickstart](https://docs.docker.com/docker-hub/)


## License & Copyright
&copy; 2022 Tien Huynh tienhuynh-tn Licensed under the [MIT LICENSE](https://github.com/tienhuynh-tn/docker-basic-tutorial/blob/main/LICENSE).

> :love_you_gesture: Feel free to use my repository and star it if you find something interesting :love_you_gesture:
