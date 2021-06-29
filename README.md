# cPanel
## Quy trình clone máy chủ dùng cPanel
- Clone máy chủ từ Template có sẵn.
- Điều chỉnh thông tin IP LAN.
- Điều chỉnh IP WAN trong file hosts.
- Điều chỉ IP trong Basic WebHost Manager:
- Thay đổi IP (cũ của template) thành IP (mới sẽ sử dụng) trong IP Migration Wizard.
- Thay đổi Hostname (cũ của template) thành hostname (mới sẽ sử dụng) trong Change Hostname.
- Cấu hình Backup cấu hình.
- Kiểm tra route tới zabbix proxy và tới cụm relay.
- Kiểm tra và thêm server mới vào Zabbix Server.
- Cấu hình filebeat theo thông tin máy chủ mới để đẩy logs qua ELK.

## Quy trình kéo disk
- Nâng thêm Disk cho máy chủ trên PVA.
- Mount CD-ROM với source Hirent Boot 15.2.
- Boot vào Hirent Boot và dùng công cụ Partition Magic để Resize Disk (kéo dài phân vùng với dung lượng mới vừa thêm). Thao tác theo các bước sau:
1. Deactived partition /dev/vda3
2. Resize/Move
3. Apply
4. Actived partition /dev/vda3

- Thực hiện cập nhật phần dung lượng mới vừa thêm bằng cách chạy command sau:
1. lvextend -l +100%FREE /dev/mailpro/lv_home
2. e2fsck -f /dev/mailpro/lv_home
3. resize2fs /dev/mailpro/lv_home

- Ngắt kết nối với CD-ROM để không Boot vào Hirent Boot mà sẽ boot vào Disk.
- Khởi động lại máy chủ.
