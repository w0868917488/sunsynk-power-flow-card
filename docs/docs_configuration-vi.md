---
myst:
  enable_extensions: ['colon_fence']
---

# Cấu hình

Thẻ có thể được cấu hình thông qua các thuộc tính sau:

| Thuộc tính             | Yêu cầu      | Mặc định                                           | Mô tả                                                                                                      |
| ---------------------- | ------------ | -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| type:                  | **Bắt buộc** | `custom:sunsynk-power-flow-card`                   | Thẻ tuỳ chỉnh.                                                                                            |
| cardstyle:             | **Bắt buộc** | `lite`                                             | Chọn bố cục thẻ sẽ sử dụng: `compact`, `lite` hoặc `full`.                                                |
| large_font:            | Tuỳ chọn     | `false`                                            | Tăng kích thước font dữ liệu cảm biến.                                                                    |
| wide:                  | Tuỳ chọn     | `false`                                            | Hiển thị nội dung của thẻ ở định dạng màn hình rộng (16:9).                                               |
| title:                 | Tuỳ chọn     |                                                   | Đặt tiêu đề thẻ, ví dụ: Inverter One.                                                                     |
| title_colour:          | Tuỳ chọn     |                                                   | Chọn màu tiêu đề thẻ. (`red`, `green`, `blue` v.v.)                                                       |
| title_size:            | Tuỳ chọn     | `32px`                                             | Đặt kích thước font cho tiêu đề thẻ, ví dụ: `16px`, `24px`.                                               |
| show_solar:            | Tuỳ chọn     | `true`                                             | Bật/tắt hiển thị thông tin năng lượng mặt trời.                                                           |
| show_battery:          | Tuỳ chọn     | `true`                                             | Bật/tắt hiển thị thông tin pin.                                                                           |
| show_grid:             | Tuỳ chọn     | `true`                                             | Bật/tắt hiển thị thông tin lưới điện.                                                                     |
| card_height:           | Tuỳ chọn     | `100%`                                             | Đặt chiều cao thẻ theo đơn vị pixel. Có thể nhập giá trị như `400px` hoặc dùng cảm biến.                  |
| card_width:            | Tuỳ chọn     | `100%`                                             | Đặt chiều rộng thẻ theo phần trăm. Có thể nhập giá trị như `80%` hoặc dùng cảm biến.                      |
| decimal_places:        | Tuỳ chọn     | `2`                                                | Số chữ số thập phân hiển thị khi dùng tuỳ chọn `auto_scale`.                                               |
| decimal_places_energy: | Tuỳ chọn     | `1`                                                | Số chữ số thập phân hiển thị cho giá trị năng lượng hàng ngày.                                             |
| dynamic_line_width:    | Tuỳ chọn     | `false`                                            | Điều chỉnh độ rộng của các đường kẻ và chấm động dựa trên tỷ lệ công suất hiện tại với `max_power`.        |
| max_line_width:        | Tuỳ chọn     | `4`                                                | Đặt độ rộng tối đa của đường kẻ khi `dynamic_line_width: true`.                                            |
| min_line_width:        | Tuỳ chọn     | `1`                                                | Đặt độ rộng tối thiểu hoặc mặc định cho đường kẻ trên thẻ.                                                 |
| inverter:              | Tuỳ chọn     | Xem thuộc tính [Inverter](#inverter) bên dưới      | Danh sách thuộc tính của inverter.                                                                        |
| battery:               | Tuỳ chọn     | Xem thuộc tính [Battery](#battery) bên dưới        | Danh sách thuộc tính của pin. Bắt buộc nếu `show_battery: true`.                                          |
| solar:                 | Tuỳ chọn     | Xem thuộc tính [Solar](#solar) bên dưới            | Danh sách thuộc tính năng lượng mặt trời.                                                                 |
| load:                  | Tuỳ chọn     | Xem thuộc tính [Load](#load) bên dưới              | Danh sách thuộc tính tải.                                                                                 |
| grid:                  | Tuỳ chọn     | Xem thuộc tính [Grid](#grid) bên dưới              | Danh sách thuộc tính lưới điện.                                                                           |
| entities:              | **Bắt buộc** | Xem thuộc tính [Entities](#entities) bên dưới      | Danh sách thực thể cảm biến.                                                                              |

### Inverter (Bộ nghịch lưu)

| Thuộc tính    | Yêu cầu   | Mặc định   | Mô tả                                                                                                   |
| ------------- | --------- | ---------- | ------------------------------------------------------------------------------------------------------- |
| modern:       | Tuỳ chọn  | `true`     | Hiển thị inverter với hình ảnh hiện đại. Đặt `false` để hiện hình ảnh dựa trên thuộc tính `model`.      |
| colour:       | Tuỳ chọn  | `grey`     | Chọn màu cho inverter và dữ liệu. Mã hex (`'#66ff00'`) hoặc tên màu (`red`, `green`, v.v.).             |
| navigate:     | Tuỳ chọn  |            | Đường dẫn điều hướng khi nhấn vào hình inverter, ví dụ: `/lovelace/1`.                                  |
| autarky:      | Tuỳ chọn  | `power`    | Hiển thị tự chủ và tỷ lệ phần trăm dựa trên công suất thời gian thực hoặc năng lượng hàng ngày.         |
| model:        | Tuỳ chọn  | `sunsynk`  | Chọn hình inverter và trạng thái. Các tuỳ chọn: `lux`, `solis`, `goodwe`, v.v.                         |
| auto_scale:   | Tuỳ chọn  | `true`     | Nếu đặt `true`, thẻ sẽ dùng thuộc tính `unit_of_measurement` để tự động chia tỷ lệ.                     |
| three_phase:  | Tuỳ chọn  | `false`    | Nếu đặt `true`, sẽ hiển thị thêm cảm biến 3 pha.                                                        |

### Battery (Pin)

Để hiển thị công suất và dòng pin dưới dạng giá trị tuyệt đối, đặt `show_absolute: true`. Mặc định là `false` và sẽ trả về giá trị cảm biến. Chấm động sẽ thay đổi hướng tuỳ thuộc vào trạng thái sạc/xả.

| Thuộc tính        | Yêu cầu   | Mặc định | Mô tả                                                                                              |
| ----------------- | --------- | -------- | -------------------------------------------------------------------------------------------------- |
| count:            | Tuỳ chọn  | `1`      | Số lượng pin hiển thị. Hai pin chỉ hiển thị khi `wide: true`.                                      |
| show_daily:       | Tuỳ chọn  | `false`  | Bật/tắt tổng năng lượng hàng ngày. Nếu `count: 2` thì là tổng giá trị của cả hai pin.              |
| animation_speed:  | Tuỳ chọn  | `6`      | Điều chỉnh tốc độ hoạt ảnh chậm nhất (giây), tuỳ vào công suất tiêu thụ.                            |
| max_power:        | Tuỳ chọn  | `4500`   | Công suất tối đa để tính tốc độ hoạt ảnh. Có thể nhập số hoặc cảm biến.                             |
| path_threshold:   | Tuỳ chọn  | `100`    | Ngưỡng áp dụng màu động cho phần đường dẫn pin.                                                     |

#### Battery One (Pin 1)

| Thuộc tính                     | Yêu cầu      | Mặc định | Mô tả                                                                                     |
| ------------------------------ | ------------ | -------- | ----------------------------------------------------------------------------------------- |
| energy:                        | **Bắt buộc** | `0`      | Tổng năng lượng pin 1 (Wh). Nếu là `0` thì ẩn thời gian còn lại.                          |
| shutdown_soc:                  | **Bắt buộc** | `20`     | Phần trăm tắt pin 1 dùng để tính thời gian còn lại.                                       |
| shutdown_soc_offgrid:          | Tuỳ chọn     |          | Phần trăm tắt pin 1 khi offgrid dùng để tính thời gian còn lại.                           |
| soc_end_of_charge:             | Tuỳ chọn     | `100`    | Đặt mức dung lượng ngắt sạc. Tối thiểu `50`, tối đa `100`.                                |
| soc_decimal_places:            | Tuỳ chọn     |          | Số chữ số thập phân hiển thị cho SOC pin. Chỉ áp dụng nếu `hide_soc: true`.               |
| invert_power:                  | Tuỳ chọn     | `false`  | Đặt `true` nếu cảm biến cung cấp số dương cho sạc, âm cho xả.                             |
| colour:                        | Tuỳ chọn     | `pink`   | Màu cho các đối tượng thẻ pin 1.                                                          |
| charge_colour:                 | Tuỳ chọn     |          | Màu cho các đối tượng thẻ pin 1 khi đang sạc.                                             |
| dynamic_colour:                | Tuỳ chọn     | `true`   | Màu biểu tượng pin 1 thay đổi dựa trên % đóng góp nguồn cấp.                               |
| linear_gradient:               | Tuỳ chọn     | `true`   | Các khối bên trong biểu tượng pin 1 sẽ dùng gradient màu từ đỏ sang xanh.                  |
| animate:                       | Tuỳ chọn     | `true`   | Hoạt ảnh gradient bên trong biểu tượng pin 1.                                              |
| show_absolute:                 | Tuỳ chọn     | `false`  | Hiển thị công suất/dòng điện dưới dạng tuyệt đối.                                          |
| auto_scale:                    | Tuỳ chọn     | `true`   | Tự động chia tỷ lệ dựa trên thuộc tính `unit_of_measurement`.                             |
| hide_soc:                      | Tuỳ chọn     | `false`  | Nếu đặt `true`, ẩn SOC hiện tại hoặc SOC shutdown.                                         |
| show_remaining_energy:         | Tuỳ chọn     | `true`   | Hiển thị năng lượng còn lại pin 1 dựa trên SOC hiện tại.                                   |
| remaining_energy_to_shutdown:  | Tuỳ chọn     | `false`  | Nếu đặt `true`, năng lượng còn lại là đến SOC tắt, không phải 0%.                          |
| navigate:                      | Tuỳ chọn     |          | Đường dẫn điều hướng khi nhấn vào hình pin 1.                                              |
| invert_flow:                   | Tuỳ chọn     | `false`  | Đảo chiều luồng hoạt ảnh.                                                                  |

#### Battery Two (Pin 2)

Tương tự như Pin 1, với các thuộc tính riêng cho pin 2.

### Solar (Năng lượng mặt trời)

Chỉ cần thiết lập nếu `show_solar: true`.

| Thuộc tính        | Yêu cầu      | Mặc định  | Mô tả                                                                                                 |
| ----------------- | ------------ | --------- | ----------------------------------------------------------------------------------------------------- |
| colour:           | Tuỳ chọn     | `orange`  | Màu cho các đối tượng thẻ mặt trời.                                                                   |
| show_daily:       | Tuỳ chọn     | `false`   | Bật/tắt tổng năng lượng hàng ngày.                                                                    |
| display_mode:     | Tuỳ chọn     | `1`       | `1` - Chỉ hiện tổng ngày, `2` - Hiện tổng ngày và dự báo còn lại, `3` - Hiện tổng ngày và tổng phát. |
| dynamic_colour:   | Tuỳ chọn     | `true`    | Các phần tử mặt trời sẽ chuyển sang màu xám nếu tổng công suất < 10W.                                 |
| mppts:            | **Bắt buộc** | `2`       | Số lượng MPPT sử dụng `1-6`. Dùng chế độ `wide` để hiển thị > 4 MPPT.                                 |
| animation_speed:  | Tuỳ chọn     | `9`       | Tốc độ hoạt ảnh chậm nhất, tuỳ vào công suất sản xuất.                                                |
| max_power:        | Tuỳ chọn     | `8000`    | Công suất tối đa để tính tốc độ hoạt ảnh và hiệu suất năng lượng mặt trời.                             |
| pv1_name:         | Tuỳ chọn     | `PV1`     | Tên hiển thị cho MPPT1.                                                                               |
| pv1_max_power:    | Tuỳ chọn     |           | Công suất tối đa MPPT1.                                                                                |
| pv2_name:         | Tuỳ chọn     | `PV2`     | Tên hiển thị cho MPPT2.                                                                               |
| pv2_max_power:    | Tuỳ chọn     |           | Công suất tối đa MPPT2.                                                                                |
| ...               | ...          | ...       | ...                                                                                                   |
| auto_scale:       | Tuỳ chọn     | `true`    | Tự động chia tỷ lệ dựa trên thuộc tính `unit_of_measurement`.                                         |
| efficiency:       | Tuỳ chọn     | `0`       | `0` - Tắt, `1` - Hiển thị đồ hoạ, `2` - Hiển thị chữ, `3` - Cả hai.                                   |
| off_threshold:    | Tuỳ chọn     | `10`      | Ngưỡng chuyển sang màu xám khi tổng công suất PV < giá trị này.                                       |
| navigate:         | Tuỳ chọn     |           | Đường dẫn điều hướng khi nhấn vào hình mặt trời.                                                      |
| invert_flow:      | Tuỳ chọn     | `false`   | Đảo chiều luồng hoạt ảnh.                                                                             |
| custom_label:     | Tuỳ chọn     |           | Đặt nhãn tuỳ chỉnh thay thế nhãn mặc định.                                                            |

### Load (Tải)

| Thuộc tính            | Yêu cầu      | Mặc định           | Mô tả                                                                                                |
| --------------------- | ------------ | ------------------ | ---------------------------------------------------------------------------------------------------- |
| colour:               | Tuỳ chọn     | `'#5fb6ad'`        | Màu cho các đối tượng tải.                                                                           |
| off_colour:           | Tuỳ chọn     | `grey`             | Màu cho tải phụ khi công suất < ngưỡng tắt.                                                          |
| max_colour:           | Tuỳ chọn     |                    | Màu ngưỡng trên cho tải phụ.                                                                         |
| dynamic_colour:       | Tuỳ chọn     | `true`             | Màu biểu tượng thiết yếu thay đổi dựa trên % nguồn cung cấp tải.                                     |
| dynamic_icon:         | Tuỳ chọn     | `true`             | Biểu tượng thiết yếu thay đổi khi có 100% đóng góp từ một nguồn.                                      |
| invert_load:          | Tuỳ chọn     | `false`            | Đặt `true` nếu cảm biến trả về giá trị âm khi tải tiêu thụ điện.                                      |
| show_daily:           | Tuỳ chọn     | `false`            | Bật/tắt tổng tải hàng ngày.                                                                          |
| show_daily_aux:       | Tuỳ chọn     | `false`            | Bật/tắt tổng AUX hàng ngày.                                                                          |
| show_aux:             | Tuỳ chọn     | `false`            | Bật/tắt hiển thị AUX.                                                                                |
| invert_aux:           | Tuỳ chọn     | `false`            | Đặt `true` nếu cảm biến trả về số dương cho AUX vào, âm cho AUX ra.                                  |
| show_absolute_aux:    | Tuỳ chọn     | `false`            | Hiển thị công suất dưới dạng tuyệt đối cho AUX.                                                      |
| animation_speed:      | Tuỳ chọn     | `8`                | Tốc độ hoạt ảnh chậm nhất tuỳ công suất tải.                                                          |
| max_power:            | Tuỳ chọn     | `8000`             | Công suất tối đa để tính tốc độ hoạt ảnh.                                                            |
| aux_name:             | Tuỳ chọn     | `Auxilary`         | Tên hiển thị cho AUX Load.                                                                           |
| ...                   | ...          | ...                | ...                                                                                                  |
| auto_scale:           | Tuỳ chọn     | `true`             | Tự động chia tỷ lệ dựa trên thuộc tính `unit_of_measurement`.                                        |
| off_threshold:        | Tuỳ chọn     | `0`                | Ngưỡng tải được coi là tắt và chuyển màu xám.                                                        |
| path_threshold:       | Tuỳ chọn     | `100`              | Ngưỡng áp dụng màu động cho đường dẫn tải.                                                           |
| navigate:             | Tuỳ chọn     |                    | Đường dẫn điều hướng khi nhấn vào biểu tượng tải thiết yếu.                                           |
| invert_flow:          | Tuỳ chọn     | `false`            | Đảo chiều luồng hoạt ảnh.                                                                            |
| label_daily_load:     | Tuỳ chọn     |                    | Nhãn tuỳ chỉnh cho "DAILY LOAD".                                                                     |

### Grid (Lưới điện)

| Thuộc tính             | Yêu cầu   | Mặc định         | Mô tả                                                                                                 |
| ---------------------- | --------- | ---------------  | ----------------------------------------------------------------------------------------------------- |
| colour:                | Tuỳ chọn  | `'#5490c2'`      | Màu cho các đối tượng lưới điện.                                                                      |
| grid_name:             | Tuỳ chọn  |                  | Tên hiển thị cho lưới điện.                                                                          |
| export_colour:         | Tuỳ chọn  |                  | Màu khi xuất năng lượng lên lưới.                                                                    |
| no_grid_colour:        | Tuỳ chọn  |                  | Màu khi không có điện lưới.                                                                          |
| grid_off_colour:       | Tuỳ chọn  |                  | Màu biểu tượng khi lưới điện bị ngắt kết nối.                                                        |
| show_daily_buy:        | Tuỳ chọn  | `false`          | Bật/tắt tổng mua điện hàng ngày.                                                                     |
| show_daily_sell:       | Tuỳ chọn  | `false`          | Bật/tắt tổng bán điện hàng ngày.                                                                     |
| show_nonessential:     | Tuỳ chọn  | `true`           | Bật/tắt hiển thị tải không thiết yếu.                                                                |
| ...                   | ...       | ...              | ...                                                                                                   |
| auto_scale:            | Tuỳ chọn  | `true`           | Tự động chia tỷ lệ dựa trên thuộc tính `unit_of_measurement`.                                        |
| energy_cost_decimals:  | Tuỳ chọn  | `2`              | Số chữ số thập phân cho chi phí năng lượng mua/bán.                                                   |
| off_threshold:         | Tuỳ chọn  | `0`              | Ngưỡng tải được coi là tắt và chuyển màu xám.                                                        |
| ...                   | ...       | ...              | ...                                                                                                   |
| navigate:              | Tuỳ chọn  |                  | Đường dẫn điều hướng khi nhấn vào biểu tượng lưới điện.                                               |
| invert_flow:           | Tuỳ chọn  | `false`          | Đảo chiều luồng hoạt ảnh.                                                                            |

### Entities (Thực thể cảm biến)

Các thuộc tính thực thể dưới đây được gắn với số hiệu thanh ghi modbus, ví dụ: `pv2_power_187`. Thay bằng cảm biến phù hợp của bạn. Nếu thiếu cảm biến cho thuộc tính nào, đặt là `none` để ẩn dữ liệu. Đặt là `zero` để hiện mặc định giá trị 0.

Xem [WIKI](https://github.com/slipx06/sunsynk-power-flow-card/wiki/Sensor-Mappings) để biết thêm thông tin về ánh xạ cảm biến.

#### Solar Entities (Thực thể mặt trời)

| Thuộc tính            | Yêu cầu   | Mặc định                                  | Mô tả                                                                                  |
| --------------------- | --------- | ----------------------------------------- | -------------------------------------------------------------------------------------- |
| day_pv_energy_108:    | Tuỳ chọn  | `sensor.sunsynk_day_pv_energy`            | Năng lượng mặt trời hàng ngày (kWh).                                                   |
| pv1_power_186:        | Tuỳ chọn  | `sensor.sunsynk_pv1_power`                | Công suất chuỗi PV1 (W).                                                               |
| ...                   | ...       | ...                                       | ...                                                                                    |
| remaining_solar:      | Tuỳ chọn  | `sensor.solcast_forecast_remaining_today` | Dự báo năng lượng mặt trời còn lại trong ngày (kWh).                                   |
| total_pv_generation:  | Tuỳ chọn  |                                           | Tổng năng lượng mặt trời phát (trọn đời hoặc dự báo trong ngày) (kWh).                 |
| ...                   | ...       | ...                                       | ...                                                                                    |

#### Battery Entities (Thực thể pin)

##### Battery One Entities (Thực thể pin 1)

| Thuộc tính                  | Yêu cầu      | Mặc định                                   | Mô tả                                                                           |
| --------------------------- | ------------ | ------------------------------------------ | -------------------------------------------------------------------------------- |
| day_battery_discharge_71:   | Tuỳ chọn     | `sensor.sunsynk_day_battery_discharge`     | Năng lượng xả pin hàng ngày (kWh). Nếu hiển thị 2 pin thì cảm biến này là tổng.  |
| day_battery_charge_70:      | Tuỳ chọn     | `sensor.sunsynk_day_battery_charge`        | Năng lượng sạc pin hàng ngày (kWh).                                              |
| battery_power_190:          | **Bắt buộc** | `sensor.sunsynk_battery_power`             | Công suất pin (W). Số âm là sạc, số dương là xả.                                 |
| battery_current_191:        | **Bắt buộc** | `sensor.sunsynk_battery_current`           | Dòng điện pin (A).                                                               |
| ...                         | ...          | ...                                        | ...                                                                              |

##### Battery Two Entities (Thực thể pin 2)

Tương tự pin 1.

#### Inverter Entities (Thực thể inverter)

| Thuộc tính               | Yêu cầu   | Mặc định                                        | Mô tả                                                                                 |
| ------------------------ | --------- | ----------------------------------------------  | ------------------------------------------------------------------------------------- |
| inverter_status_59:      | Tuỳ chọn  | `sensor.sunsynk_overall_state`                  | Trạng thái inverter.                                                                  |
| ...                      | ...       | ...                                             | ...                                                                                   |

#### Load Entities (Thực thể tải)

| Thuộc tính              | Yêu cầu   | Mặc định                          | Mô tả                                                      |
| ----------------------- | --------- | -------------------------------- | ----------------------------------------------------------- |
| day_load_energy_84:     | Tuỳ chọn  | `sensor.sunsynk_day_load_energy` | Tải hàng ngày (kWh).                                       |
| ...                     | ...       | ...                              | ...                                                         |

#### Grid Entities (Thực thể lưới điện)

| Thuộc tính                  | Yêu cầu      | Mặc định                                       | Mô tả                                                      |
| --------------------------- | ------------ | ---------------------------------------------  | ---------------------------------------------------------- |
| day_grid_import_76:         | Tuỳ chọn     | `sensor.sunsynk_day_grid_import`               | Nhập điện lưới hàng ngày (kWh).                           |
| ...                         | ...          | ...                                            | ...                                                        |

Thẻ tự động tính các cảm biến dựa trên cấu hình, không cần định nghĩa trong Home Assistant. Nếu đọc sai giá trị thiết yếu/không thiết yếu, thay cảm biến 169 bằng 167 hoặc cung cấp cảm biến tự tính toán.

Nếu `three_phase:false`

```
totalsolar = pv1_power_186 + pv2_power_187 + pv3_power_188 + pv4_power_189
nonessential = grid_ct_power_172 - grid_power_169
essential = inverter_power_175 + grid_power_169 - aux_power_166
```

Nếu `three_phase:true`

```
totalsolar = pv1_power_186 + pv2_power_187 + pv3_power_188 + pv4_power_189
nonessential = grid_ct_power_172 + grid_ct_power_L2 + grid_ct_power_L3 - grid_power_169
essential =  load_power_L1 +  load_power_L2 +  load_power_L3
```

Các thanh ghi modbus có thể được trực quan hóa trên thẻ `full` bên dưới:

![sunsynk_reg](https://github.com/user-attachments/assets/2c42a4e7-b4a2-4dd3-b019-14e1bd642d68)
