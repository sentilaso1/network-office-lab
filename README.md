# 🏢 Office Network Simulation – Cisco Packet Tracer

## 🔍 Mô tả dự án
Dự án mô phỏng mạng nội bộ cho một văn phòng gồm 3 phòng ban: IT, Kế toán, và Nhân sự. Sử dụng Cisco Packet Tracer để thiết lập VLAN, DHCP, NAT và ACL.

## 📐 Sơ đồ mạng


## 📁 Cấu trúc mạng
| Phòng ban   | VLAN | Mạng IP           | Gateway         |
|-------------|------|-------------------|-----------------|
| IT          | 10   | 192.168.10.0/24   | 192.168.10.1    |
| Kế toán     | 20   | 192.168.20.0/24   | 192.168.20.1    |
| Nhân sự     | 30   | 192.168.30.0/24   | 192.168.30.1    |

## 🧪 Tính năng triển khai
- ✅ VLAN segmentation
- ✅ DHCP cho từng VLAN
- ✅ NAT để truy cập Internet
- ✅ ACL chặn truy cập giữa các phòng
- ✅ Giao tiếp nội bộ giữa cùng VLAN

## 🛠 Công cụ sử dụng
- Cisco Packet Tracer
- Markdown
- draw.io

## 📦 File đính kèm
- `packet-tracer.pkt`: Mô hình mạng Packet Tracer
- `config-commands.txt`: Cấu hình Router và Switch
- `report.pdf`: Báo cáo tổng hợp

## 📚 Hướng phát triển
- Thêm hệ thống DNS nội bộ
- Cấu hình firewall nâng cao
- Kết nối chi nhánh khác bằng VPN

