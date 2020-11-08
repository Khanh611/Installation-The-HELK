Hướng dẫn cài đặt The HELK trên ubuntu 20.04
===============

.. contents :: **Mục lục**

Yêu cầu phần cứng
---------------------

- Hệ điều hành: Ubuntu 20.04
- Cores: 4 cores
- Network: NAT hoặc Bridge
- RAM: có 4 option và dưới đây là yêu cầu tối thiểu

    + Option 1: 5GB bao gồm KAFKA + KSQL + ELK + NGNIX.
    + Option 2: 5GB bao gồm KAFKA + KSQL + ELK + NGNIX + ELASTALERT.
    + Option 3: 7GB bao gồm KAFKA + KSQL + ELK + NGNIX + SPARK + JUPYTER.
    + Option 4: 8GB bao gồm KAFKA + KSQL + ELK + NGNIX + SPARK + JUPYTER + ELASTALERT.
- Disk: 40GB

Tải về The HELK
----------------

- Cài đặt ``git`` bằng lệnh:

::

    sudo apt-get install git

- Clone source code về bằng lệnh:

::

    git clone https://github.com/Cyb3rWard0g/HELK.git

.. figure:: https://user-images.githubusercontent.com/65669673/98461298-99fe4900-21dd-11eb-812d-0351351a5c61.PNG


Cài đặt The HELK
----------------

- Để giúp mọi người cài đặt HELK dễ dàng, dự án đi kèm với một tập lệnh cài đặt có tên là ``helk_install.sh``. Tập lệnh này tự động xây dựng và chạy mọi thứ cho HELK.
- Để chạy tập lệnh ``helk_install.sh`` ta vào thư mục HELK và chạy lệnh:

::

    cd HELK/docker
    sudo ./helk_install.sh

- Trong quá trình cài đặt sẽ thiết lập những thứ sau:

    + Enter build choice: Chọn option muốn cài đặt
    + Set HELK IP: Đặt địa chỉ IP cho HELK
    + Set HELK Kibana UI Password: Đặt mật khẩu cho người dùng Kibana

.. figure:: https://user-images.githubusercontent.com/65669673/98461322-cfa33200-21dd-11eb-8159-bd1e4bcc14af.PNG

- Sau khi thiết lập xong thì quá trình cài đặt sẽ diễn ra tự động

.. figure:: https://user-images.githubusercontent.com/65669673/98461329-e21d6b80-21dd-11eb-96ce-10feecd48467.PNG

Theo dõi quá trình cài đặt The HELK
------------------------------------

- Khi quá trình cài đặt bắt đầu, nó sẽ bắt đầu hiển thị các thông báo được xác định trước về quá trình cài đặt, nhưng không có tất cả các chi tiết về những gì đang thực sự xảy ra trong nền. Nó được thiết kế theo cách đó để giữ cho màn hình chính luôn sạch sẽ và cho biết nó đang ở đâu trong quá trình cài đặt.
- Những gì được khuyên trong HELK là mở một terminal khác và theo dõi quá trình cài đặt HELK bằng lệnh sau:

::

    tail -f /var/log/helk-install.log


.. figure:: https://user-images.githubusercontent.com/65669673/98461332-e77ab600-21dd-11eb-8920-2a6a7a91e90c.PNG

- Khi thấy rằng các containers đã được tạo, có thể kiểm tra tất cả các containers đang chạy bằng cách thực hiện như sau:

::

    sudo docker ps

.. figure:: https://user-images.githubusercontent.com/65669673/98461413-7982be80-21de-11eb-8272-c3528263d369.png

- Nếu muốn theo dõi các tài nguyên đang được sử dụng (RAM, CPU,...), có thể chạy như sau:

::

    sudo docker stats --all


.. figure:: https://user-images.githubusercontent.com/65669673/98461431-9e773180-21de-11eb-9f76-a3f8144b8ed2.png


Truy cập vào The HELK
----------------------

- Khi quá trình cài đặt HELK kết thúc, ta sẽ được cung cấp thông tin cần thiết để truy cập HELK và tất cả các thành phần khác của nó.

.. figure:: https://user-images.githubusercontent.com/65669673/98461335-e9dd1000-21dd-11eb-97d6-3c7ef308ab07.PNG

- Để truy cập vào KIBANA thì ta mở trình duyệt lên và truy cập vào địa chỉ host của HELK KIBANA và đăng nhập với Tên người dùng là helk và Mật khẩu như đã đặt trong quá trình cài đặt

.. figure:: https://user-images.githubusercontent.com/65669673/98461447-c1094a80-21de-11eb-952c-6c984061ac27.PNG

.. figure:: https://user-images.githubusercontent.com/65669673/98461338-ed709700-21dd-11eb-90d0-0cefe910e1c1.PNG

