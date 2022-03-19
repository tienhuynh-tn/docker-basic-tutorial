# Chương 7: Duy trì dữ liệu - Persist the DB

Có thể bạn không chú ý đến điều này, rằng danh sách những việc cần làm trong todo-list của chúng ta bị xóa sạch sẽ mỗi lần chúng ta khởi chạy container. Tại sao? Hãy đi sâu vào cách thức hoạt động của container để hiểu thêm về nó.

## Table of Contents
- [Hệ thống tập tin của container - The container’s filesystem](#hệ-thống-tập-tin-của-container---the-container's-filesystem)
  - [See this in practice](#see-this-in-practice)
- [Container volumes](#container-volumes)
- [Persist the todo data](#persist-the-todo-data)
- [Dive into the volume](#dive-into-the-volume)
- [Recap - Tổng kết](#recap----tổng-kết)
- [Reference](#reference)
- [License & Copyright](#license--copyright)

## Hệ thống tập tin của container - The container’s filesystem

Khi một container chạy, nó sử dụng các lớp khác như từ một image cho hệ thống tập tin của nó. Mỗi container cũng có "scratch space" của riêng nó để tạo/cập nhật/xóa các file. Mọi thay đối sẽ không được nhìn thấy trong một container khác, ngay cả khi chúng đang sử dụng cùng một image.

### See this in practice

Để thấy được những điều trên trong thực tế, chúng ta sẽ khởi động 2 containers và tạo một file trong mỗi container đó. Cái mà bạn sẽ thấy được là các files được tạo trong một container không khả dụng trong container còn lại.

1. Khởi động một container `ubuntu` cái mà sẽ tạo ra một file có tên `/data.txt` với một con số random giữa 1 và 10 000.

```
docker run -d ubuntu bash -c "shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null"
```

Trong trường hợp bạn tò mò về câu lệnh, chúng ta khởi động một bash shell và gọi hai lệnh (lý do chúng ta có `&&`). Phần đầu tiên chọn một số ngẫu nhiên và viết nó vào `/data.txt`. Dòng lệnh thứ hai chỉ đơn giản là xem một tệp để giữ cho container chạy.

## Container volumes

## Persist the todo data

## Dive into the volume

## Recap  - Tổng kết

## Reference
- [Docker Documentation](https://docs.docker.com/get-started/)
- [Get started - Part 5: Persist the DB](https://docs.docker.com/get-started/05_persisting_data/)

## License & Copyright
&copy; 2022 Tien Huynh tienhuynh-tn Licensed under the [MIT LICENSE](https://github.com/tienhuynh-tn/docker-basic-tutorial/blob/main/LICENSE).

> :love_you_gesture: Feel free to use my repository and star it if you find something interesting :love_you_gesture:

