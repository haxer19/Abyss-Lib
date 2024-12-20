# Abyss-Lib

## 1. **Giới thiệu**
Thư viện này giúp bạn tạo các giao diện UI chính trong Roblox một cách dễ dàng. Bạn có thể tạo các tab, button, slider, toggle, color picker, v.v.

---

## 2. **Khởi tạo thư viện**

### **Mã khởi tạo thư viện**
```lua
local Ui = loadstring(game:HttpGet("https://raw.githubusercontent.com/haxer19/Abyss-Lib/refs/heads/main/soucre.lua"))()
local Ui = Library
```
**Giải thích:**
- Tải và khởi tạo thư viện từ URL.
- Biến `Library` chứa toàn bộ các chức năng tạo giao diện UI.

---

## 3. **Tạo loader và cửa sổ chính**

### **Tạo Loader**
```lua
local Loader = Library.CreateLoader("Tên Loader", Vector2.new(300, 300))
```
**Giải thích:**
- Hiện thị cửa sổ chờ load.
- Thông số `Vector2.new(300, 300)` là kích thước của loader.

### **Tạo cửa sổ UI**
```lua
local Window = Library.Window("Tên cửa sổ", Vector2.new(500, 620))
```
**Giải thích:**
- Tạo cửa sổ giao diện chính.
- Thông số `Vector2.new(500, 620)` là kích thước của cửa sổ.

---

## 4. **Thông báo và watermark**

### **Thông báo (Notification)**
```lua
Window.SendNotification("Normal", "Nhấn RightShift để mở/ đóng menu!", 10)
```
**Giải thích:**
- Hiện thông báo với nội dung "Nhấn RightShift để mở/đóng menu!" trong 10 giây.

### **Watermark**
```lua
Window.Watermark("Tên watermark")
```
**Giải thích:**
- Thêm watermark vào giao diện.

---

## 5. **Thêm Tab và Section**

### **Tạo Tab**
```lua
local Tab1 = Window:Tab("Tên Tab")
```
**Giải thích:**
- Thêm một tab vào cửa sổ.

### **Tạo Section**
```lua
local Section1 = Tab1:Section("Tên Section", "Left")
```
**Giải thích:**
- Thêm section vào tab.

---

## 6. **Thêm các phần tử UI**

### **Toggle**
```lua
Section1:Toggle({
    Title = "Tên Toggle",
    Flag = "Flag_Toggle",
    Callback = function(v)
        print("Giá trị = "..v)
    end
})
```
**Giải thích:**
- Thêm một toggle có callback khi người dùng bật/tắt.

### **Slider**
```lua
Section1:Slider({
    Title = "Tên Slider",
    Default = 0,
    Min = 0,
    Max = 20,
    Callback = function(v)
        print("Giá trị = "..v)
    end
})
```
**Giải thích:**
- Thêm một thanh slider từ 0 đến 20.

### **Dropdown**
```lua
Section1:Dropdown({
    Title = "Tên Dropdown",
    List = {"1", "2", "3"},
    Default = "1",
    Callback = function(v)
        print("Giá trị = "..v)
    end
})
```
**Giải thích:**
- Tạo một dropdown với 3 lựa chọn.

### **Button**
```lua
Section1:Button({
    Title = "Tên Button",
    Callback = function()
        print("Button đã nhấn!")
    end
})
```
**Giải thích:**
- Tạo một nút bấm và thực hiện hàm Callback khi bấm.

---

## 7. **Cài đặt và chức năng thêm**

### **Chức năng thêm**
```lua
Window:AddSettingsTab()
Window:SwitchTab(Tab1)
Window.ToggleAnime(false)
```
**Giải thích:**
- Thêm tab cài đặt.
- Chuyển sang tab 1.
- Tắt hiệu ứng chuyển đổi.

