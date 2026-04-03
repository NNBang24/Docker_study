```sh
docker run <image_name> # gan cho 1 cai ten random
docker run --name <container_name> <image_name> # /cach dat ten cua container va image
///
docker run hello-world
docker run -it ubuntu bash

# 1() Docker commands and Docker container

docker ps  # Xem các container đang chạy
docker ps -a # Xem TẤT CẢ container (kể cả đã dừng)

docker rm <container_id_or_name> # Xóa container đã dừng (stopped)
docker rm -f <container_id_or_name> # Ép xóa container (force)

docker stop <container_id_or_name> #  DỪNG container
docker start <container_id_or_name> # CHẠY LẠI container đã dừng
docker restart <container_id_or_name> # KHỞI ĐỘNG LẠI container

docker inspect <container_id_or_name> #Xem thông tin chi tiết của container (dưới dạng JSON)

docker run -d <image_name> # chạy container ở chế độ nền (detached mode (chạy ngầm))  VA CHAY CONTAINER O BACKGROUND

# chạy container và vào terminal bên trong (-i = interactive (cho nhập) va  -t = terminal (hiển thị đẹp) /bin/bash = mở shell trong container)
docker run -it <image_name> /bin/bash 

docker run -p <host_port>:<container_port> <image_name> #map (kết nối) port từ container ra máy thật của bạn (docker run -p 8080:80 nginx)

docker logs <container_id_or_name>   #Xem toàn bộ log đã in ra của container (đén thời điểm hiện tại)
docker logs -f <container_id_or_name>   # Xem log theo thời gian thực (real-time) (xem log được update liên tục khi container đang chạy  = > muốn monitor)

# cleaning up 
##( Một số container đã dừng (exited) vì hoàn thành công việc hoặc bị lỗi )
## Những container này không tự biến mất , mà vẫn chiếm dung lượng ổ cứng và tài nguyễn metadata của Docker
docker container prune #(có hỏi xác nhận xóa hay không)
docker container prune -f #(thêm cờ -f để tự động đông ý) 

docker exec -it <container_id_or_name> <command> #chạy lệnh bên trong container đang chạy (execute : thực thi )
vd :  docker exec -it ec884143c379 bash

# tao container
docker run -d -it --name my-cob --restart always ubuntu:latest bash
///

# 2 ) Docker images 
docker pull <image_name>:<tag>  #(quan trong )
# Tên của imgae , nếu trên docker hub sẽ là tên của repository (quan trong )
# ví dụ : ubuntu ,my_app ,nginx
# tag : là nhãn (label) chỉ định phiên bản cụ thể của image
# ví dụ : latest ,20.04 ,v1.0   

docker images # Kiểm tra các image đang có trong máy local
#cùng 1 image có thẻ nhiều tag 


# Các lệnh xóa images 

## Đây là cách viết ngắn gọn 
docker rmi <image_name>:<tag>
docker rmi <image_id>

#đây là cách xóa khi có container đang chạy
docker rmi -f <image_id>
## cách viết chính quy

docker image rm <image_name>:<tag>
docker image rm <image_id>



ls #la liet ke cac thu muc
whoami # la ten la gi
pwd # In ra đường dẫn thư mục hiện tại
exit # la thoat khoi muc hien tai
echo # in ra  man hinh 
///

```