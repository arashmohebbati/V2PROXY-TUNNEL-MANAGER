# 🚀 V2PROXY TUNNEL MANAGER

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-Linux-green.svg)
![Status](https://img.shields.io/badge/status-stable-success.svg)

<p align="center">
  <img src="assets/banner.png" alt="V2PROXY TUNNEL MANAGER" />
</p>

---

## 📖 معرفی

**V2PROXY TUNNEL MANAGER** یک ابزار قدرتمند مبتنی بر **Bash** است که برای مدیریت آسان و خودکار تونل‌های **GRE (IPv4 و IPv6)** طراحی شده است.  
این ابزار به شما کمک می‌کند:

✅ به‌سرعت تونل‌های GRE ایجاد و مدیریت کنید.  
✅ وضعیت تونل‌ها را بررسی و در صورت نیاز حذف کنید.  
✅ برای بوت خودکار، سرویس **systemd** ایجاد نمایید.  

این اسکریپت مخصوص **ساده‌سازی فرآیندهای پیچیده شبکه** و ایجاد اتصالات امن و پایدار طراحی شده است.

---

## ✨ ویژگی‌ها

- **پشتیبانی از GRE IPv4 و IPv6** (مدیریت همزمان هر دو نوع تونل)  
- **ایجاد و حذف آسان تونل** با رابط کاربری تعاملی  
- **مدیریت پیکربندی خودکار:** ذخیره اطلاعات در فایل `tunnels.conf`  
- **بررسی وضعیت تونل‌ها** (لیست تونل‌های فعال)  
- **راه‌اندازی خودکار (Autostart):** با استفاده از سرویس **systemd**  
- **پشتیبانی از MikroTik:** ارائه دستورات آماده برای سمت میکروتیک  
- **نام‌گذاری خودکار:** ایجاد نام‌های یونیک برای تونل‌ها  
- **رابط کاربری رنگی و خوانا**  

---

## ✅ پیش‌نیازها

- **سیستم عامل:** توزیع‌های مبتنی بر Debian/Ubuntu  
- **دسترسی:** دسترسی root برای اجرای برخی دستورات  
- **بسته‌های مورد نیاز:**

```bash
sudo apt install iproute2 dialog util-linux -y
```

---

## 🛠️ نصب

### 1. دریافت اسکریپت

```bash
git clone https://github.com/arashmohebbati/v2proxy-tunnel-manager.git
cd v2proxy-tunnel-manager
```

### 2. اجرایی کردن اسکریپت

```bash
chmod +x v2proxy-tunnel-manager.sh
```

### 3. (اختیاری) راه‌اندازی خودکار با systemd

```bash
sudo cp v2proxy-tunnel-manager.sh /usr/local/bin/v2proxy-tunnel-manager.sh
```

سپس فایل سرویس را ایجاد و فعال کنید:

```bash
sudo bash -c 'cat > /etc/systemd/system/v2proxy-tunnel.service <<EOF
[Unit]
Description=V2PROXY Tunnel Manager Service
After=network.target

[Service]
ExecStart=/usr/local/bin/v2proxy-tunnel-manager.sh --autostart
Restart=on-failure
User=root

[Install]
WantedBy=multi-user.target
EOF'

sudo systemctl enable v2proxy-tunnel.service
sudo systemctl start v2proxy-tunnel.service
```

---

## 📚 نحوه استفاده

برای اجرای اسکریپت:

```bash
./v2proxy-tunnel-manager.sh
```

پس از اجرا، یک **منوی تعاملی رنگی** برای مدیریت تونل‌ها نمایش داده می‌شود.

---

## 🔥 بنر ترمینال (ASCII Art)

در ترمینال هنگام اجرای اسکریپت، بنر زیبای زیر نمایش داده می‌شود:

```
░██    ░██  ░██████  ░█████████  ░█████████    ░██████   ░██    ░██ ░██     ░██ 
░██    ░██ ░██   ░██ ░██     ░██ ░██     ░██  ░██   ░██   ░██  ░██   ░██   ░██  
░██    ░██       ░██ ░██     ░██ ░██     ░██ ░██     ░██   ░██░██     ░██ ░██   
░██    ░██   ░█████  ░█████████  ░█████████  ░██     ░██    ░███       ░████    
 ░██  ░██   ░██      ░██         ░██   ░██   ░██     ░██   ░██░██       ░██     
  ░██░██   ░██       ░██         ░██    ░██   ░██   ░██   ░██  ░██      ░██     
   ░███    ░████████ ░██         ░██     ░██   ░██████   ░██    ░██     ░██     
                    		    												
```

---

## 📜 لایسنس

این پروژه تحت لایسنس **MIT** منتشر شده است. برای جزئیات بیشتر فایل [LICENSE](LICENSE) را ببینید.

---

## 🔗 لینک‌ها

- **Telegram:** [v2proxy](https://t.me/v2proxy)  
- **GitHub:** [V2PROXY TUNNEL MANAGER](https://github.com/arashmohebbati/v2proxy-tunnel-manager)

---

### ❤️ حمایت

اگر این پروژه برای شما مفید بود، با ⭐ دادن در گیت‌هاب از ما حمایت کنید!

EOF
