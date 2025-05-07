# RankElo

Plugin hệ thống Elo cho các máy chủ Minecraft, cho phép xếp hạng người chơi dựa trên kỹ năng PvP.

## Tính năng

- **Hệ thống điểm Elo**: Người chơi nhận và mất điểm khi tiêu diệt hoặc bị tiêu diệt bởi người chơi khác
- **Nhiều cấp độ (tier) với phần thưởng**: Khi đạt được các mốc điểm Elo, người chơi nhận được phần thưởng
- **Lưu trữ dữ liệu linh hoạt**: 
  - Hỗ trợ lưu trữ theo UUID riêng biệt cho từng người chơi (tương tự Essentials)
  - Dữ liệu người chơi được lưu trong các file riêng theo UUID
  - Lưu dữ liệu tự động khi có thay đổi điểm Elo
- **Hệ thống Combat Log**: 
  - Ngăn người chơi thoát game khi đang PvP
  - Trừ điểm Elo khi thoát game trong lúc PvP
  - Tùy chọn bật/tắt thông báo combat log
- **Hệ thống mùa giải**:
  - Lưu lại thông tin điểm Elo, xếp hạng, tier và số kill của người chơi theo mỗi mùa giải
  - Cài đặt thời gian mùa giải linh hoạt theo phút (mặc định: 43200 phút = 30 ngày)
  - Giao diện GUI thân thiện để xem lịch sử mùa giải
  - Tùy chọn reset điểm Elo và số kill khi mùa giải kết thúc
- **Theo dõi Kill trong mùa giải**:
  - Theo dõi số kill của mỗi người chơi trong mỗi mùa giải
  - Hiển thị số kill trong GUI mùa giải
  - Reset số kill khi bắt đầu mùa giải mới
- **Hệ thống chống farm Elo**: 
  - Giới hạn số lần nhận điểm Elo khi giết cùng một người chơi
  - Phát hiện farm Elo từ cùng IP
- **Hỗ trợ giới hạn thế giới**: Có thể cấu hình các thế giới không tính điểm Elo
- **Hỗ trợ PlaceholderAPI**: Dễ dàng hiển thị thông tin Elo trên scoreboard, tablist,...
- **Hệ thống lệnh đầy đủ**: Kiểm tra, đặt, thêm, trừ điểm Elo và xem top xếp hạng
- **Tương thích với nhiều phiên bản Minecraft** (1.8.8 đến 1.21.4)

## Lệnh

### Lệnh cơ bản
- `/elo check [player]` - Kiểm tra điểm Elo của bản thân hoặc người chơi khác
- `/elo top [limit]` - Hiển thị top người chơi có điểm Elo cao nhất
- `/elo help` - Hiển thị danh sách lệnh
- `/season` - Hiển thị giao diện GUI lịch sử mùa giải (hoặc `/eloseason`)

### Lệnh Admin
- `/elo set <player> <elo>` - Đặt điểm Elo cho người chơi
- `/elo reset <player>` - Đặt lại điểm Elo của người chơi về mặc định
- `/elo add <player> <amount>` - Thêm điểm Elo cho người chơi
- `/elo taken <player> <percent>` - Trừ một phần trăm điểm Elo của người chơi
- `/elo reload` - Tải lại cấu hình

## Quyền

- `rankelo.check` - Cho phép kiểm tra điểm Elo của bản thân và người chơi khác
- `rankelo.top` - Cho phép xem danh sách top người chơi
- `rankelo.season` - Cho phép xem thông tin mùa giải
- `rankelo.admin` - Cho phép sử dụng tất cả các lệnh quản trị

## Placeholders

Plugin hỗ trợ các placeholder sau (yêu cầu PlaceholderAPI):

- `%rankelo_points%` - Điểm Elo của người chơi
- `%rankelo_tier%` - Tier hiện tại của người chơi (1, 2, 3)
- `%rankelo_tier_name%` - Tên của tier hiện tại
- `%rankelo_tier_progress%` - Tiến độ trong tier hiện tại (%)
- `%rankelo_tier_progress_bar%` - Thanh tiến độ trong tier hiện tại
- `%rankelo_position%` - Vị trí xếp hạng của người chơi
- `%rankelo_top_name_X%` - Tên của người chơi ở vị trí X (top_name_1, top_name_2, ...)
- `%rankelo_top_points_X%` - Điểm của người chơi ở vị trí X (top_points_1, top_points_2, ...)
- `%rankelo_kills%` - Số kill của người chơi trong mùa hiện tại
- `%rankelo_kills_season_X%` - Số kill của người chơi trong mùa X
- `%rankelo_top_kills_X%` - Số kill của người chơi ở vị trí X trong bảng xếp hạng kill
- `%rankelo_top_kills_name_X%` - Tên của người chơi ở vị trí X trong bảng xếp hạng kill

## Cấu hình

Plugin có file cấu hình chi tiết cho phép tùy chỉnh:

### Cài đặt cơ bản
- Loại lưu trữ dữ liệu (YAML, SQLite, MySQL)
- Thời gian tự động lưu dữ liệu
- Các thế giới không tính điểm Elo
- Cho phép nhận phần thưởng khi tụt hạng

### Hệ thống mùa giải
- Bật/tắt chức năng mùa giải
- Thời gian giữa các mùa giải (phút)
- Thông báo khi kết thúc mùa giải
- Tự động reset điểm Elo về mặc định khi kết thúc mùa
- Cài đặt giao diện GUI (tiêu đề, số hàng, hiển thị item)
- Tùy chọn hiển thị số kill trong lore của item mùa giải
- Tùy chọn reset số kill khi bắt đầu mùa giải mới

### Hệ thống Combat Log
- Bật/tắt chức năng Combat Log
- Thời gian combat (giây)
- Phần trăm điểm Elo bị trừ khi combat log
- Bật/tắt thông báo combat log

### Chống spam Elo
- Bật/tắt chức năng chống spam
- Thời gian giới hạn (giờ)
- Số lần tối đa được giết cùng một người
- Số lần tối đa được giết người từ cùng IP

### Hệ thống điểm Elo
- Điểm Elo mặc định cho người chơi mới
- Cấu hình các tier với điểm min/max, điểm nhận/mất khi PvP
- Phần thưởng cho mỗi tier (thông báo và lệnh)

### Thông báo
- Prefix của plugin
- Các thông báo trong game
- Thông báo khi combat log
- Thông báo mùa giải

## Cấu trúc dữ liệu

Dữ liệu được lưu trữ theo từng người chơi:

- **Lưu trữ theo UUID**: 
  - Mỗi người chơi có một file riêng theo định dạng `<UUID>.yml` trong thư mục `plugins/RankElo/playerdata/`
  - Mỗi file chứa đầy đủ thông tin về điểm Elo, tier, kills và dữ liệu mùa giải của người chơi đó
  - Mô hình lưu trữ tương tự Essentials, tối ưu cho server với nhiều người chơi
  - Dữ liệu được tự động tải khi người chơi tham gia và xóa khỏi bộ nhớ khi người chơi thoát game

Cấu trúc file người chơi (`playerdata/<UUID>.yml`):
```yaml
elo: 1500                  # Điểm Elo hiện tại
max_tier: 3                # Tier cao nhất đã đạt được
kills:                     # Số kill theo mùa
  season1: 20
  season2: 13
  season3: 42
seasons:                   # Lịch sử mùa giải
  season1:
    timestamp: 1622548800  # Thời gian kết thúc mùa (Unix timestamp)
    elo: 1550              # Điểm Elo đạt được khi kết thúc mùa
    rank: 5                # Xếp hạng trong mùa
    tier: "Cao Thủ"        # Tên tier đạt được
    kills: 20              # Số kill trong mùa
  season2:
    # thông tin tương tự...
```

## Yêu cầu

- Java 8 trở lên
- Minecraft Server 1.8.8 - 1.21.4 (Spigot, Paper, ...)
- PlaceholderAPI (không bắt buộc, nhưng khuyến khích)

## Cài đặt

1. Tải xuống file plugin từ trang chủ
2. Đặt file JAR vào thư mục `plugins` của server
3. Khởi động lại server
4. Tùy chỉnh file cấu hình trong `plugins/RankElo/config.yml`
5. Sử dụng lệnh `/elo reload` để áp dụng các thay đổi

## Tác giả

Plugin được tạo bởi Nhân Shiba. 
