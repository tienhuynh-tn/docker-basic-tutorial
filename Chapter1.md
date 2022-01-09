# Chương 1: Tổng quan về Docker - Docker overview

Docker là một nền tảng mở cho việc phát triển, vận chuyển và chạy các ứng dụng. 

## Table of Contents
- [Nền tảng Docker - The Docker platform](#1-nền-tảng-docker---the-docker-platform)
- [Tôi có thể sử dụng Docker để làm gì? - What can I use Docker for?](#2-tôi-có-thể-sử-dụng-docker-để-làm-gì---what-can-i-use-docker-for)
- [Kiến trúc Docker - Docker architecture](#3-kiến-trúc-docker---docker-architecture)
- [Reference](#reference)
- [License & Copyright](#license--copyright)

## 1. Nền tảng Docker - The Docker platform

- Docker cung cấp khả năng đóng gói và chạy một ứng dụng trong một môi trường độc lập được gọi là container (thùng chứa)
- Các container có kích thước nhỏ ("trọng lượng nhẹ") và chứa mọi thứ cần thiết để chạy ứng dụng. Thường chứa các thư viện, môi trường,...

### Ví dụ thực tế:
- Khi bạn có một trang web với các công nghệ sau: Front-end cần ReactJS, Back-end cần NodeJS và SQLServer cho Database. Vấn đề đặt ra khi khách hàng muốn chạy phần mềm của bạn thì chẳng lẽ họ phải cài đặt các công nghệ đó chỉ để chạy phần mềm hay web của bạn.
- Hoặc khi bạn làm việc trong một nhóm, gồm 3 bạn A B và C, và nhóm bạn cùng phát triển một dự án làm web. Bạn A dùng hệ điều hành Window, bạn B và C lại dùng hệ điều hành Linux. Vậy khi các bạn cùng phát triển dự án này, thì các công nghệ dùng trong dự án của các bạn sẽ không được tương thích với các thành viên còn lại.
- Và còn rất nhiều ví dụ khác thể hiện cho tầm quan trọng của sử dụng Docker trong việc phát triển, vận chuyển và chạy các ứng dụng.

## 2. Tôi có thể sử dụng Docker để làm gì? - What can I use Docker for?

### Fast, consistent delivery of your applications - Phân phối nhanh chóng, nhất quán các ứng dụng của bạn
- Docker cho phép các nhà phát triển phần mềm làm việc trong các môi trường chuẩn hóa sử dụng local container, cái mà cung cấp các ứng dụng và dịch vụ của bạn. Container là ý tưởng tuyệt vời cho quy trình CI/CD
- Ví dụ:
  - Các nhà phát triển viết phần mềm ở local và chia sẻ công việc với đồng nghiệp bằng cách sử dụng Docker containers
  - Họ sử dụng Docker để đẩy ứng dụng của họ vào môi trường thử nghiệm và thực hiện các automated và manual tests
  - Khi các nhà phát triển tìm thấy lỗi, họ có thể sửa chúng trong môi trường phát triển và triển khai lại chúng vào môi trường thử nghiệm để kiểm tra và xác nhận

### Responsive deployment and scaling - Triển khai đáp ứng và mở rộng quy mô
- Docker có thể chạy trên máy tính xách tay cục bộ của nhà phát triển, trên máy vật lý hoặc máy ảo trong trung tâm dữ liệu, trên các nhà cung cấp đám mây hoặc trong một hỗn hợp các môi trường.
- Tính di động và bản chất nhẹ của Docker cũng giúp bạn dễ dàng quản lý động khối lượng công việc, mở rộng hoặc chia nhỏ các ứng dụng và dịch vụ khi nhu cầu kinh doanh yêu cầu, trong thời gian thực.

### Running more workloads on the same hardware - Chạy nhiều khối lượng công việc hơn trên cùng một phần cứng

## 3. Kiến trúc Docker - Docker architecture

- Docker sử dụng kiến trúc client-server

![Docker Architecture](https://docs.docker.com/engine/images/architecture.svg)

- Docker daemon (dockerd): lắng nghe các yêu cầu API Docker và quản lý các đối tượng Docker như images, containers, networks, and volumes. Một daemon cũng có thể giao tiếp với các daemon khác để quản lý các dịch vụ Docker. 
- Docker client: là cách chính mà nhiều người dùng Docker tương tác với Docker. Khi bạn sử dụng các lệnh như docker run, máy khách sẽ gửi các lệnh này đến dockerd để thực hiện chúng. Lệnh docker sử dụng API Docker. Docker client có thể giao tiếp với nhiều hơn một daemon. Hay nói cách khác, Docker client là cách bạn tương tác với docker thông qua các lệnh và sử dụng API để gửi lệnh đến Docker daemon
- Docker Desktop: cho phép bạn xây dựng và chia sẻ các ứng dụng và dịch vụ vi mô được chứa trong vùng chứa. Docker Desktop bao gồm Docker daemon (dockerd), Docker client (docker), Docker Compose, Docker Content Trust, Kubernetes và Credential Helper.
- Docker registries: lưu trữ Docker images. Docker Hub là một public registry mà bất kỳ ai cũng có thể sử dụng và Docker được định cấu hình để tìm kiếm images trên Docker Hub theo mặc định. 
- Docker object
  -  Images: là một mẫu read-only với các hướng dấn dành cho tạo một docker container
  -  Containers: is a runnable instance of an image

## Reference
- [Docker overview](https://docs.docker.com/get-started/overview/)


## License & Copyright
&copy; 2022 Tien Huynh tienhuynh-tn Licensed under the [MIT LICENSE](https://github.com/tienhuynh-tn/docker-basic-tutorial/blob/main/LICENSE).

> :love_you_gesture: Feel free to use my repository and star it if you find something interesting :love_you_gesture:
