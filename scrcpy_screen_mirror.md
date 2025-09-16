`scrcpy` adalah aplikasi open-source yang memungkinkan kamu menampilkan dan mengontrol layar Android di PC/laptop lewat USB (atau WiFi). Ringan, tanpa root, dan gratis. Berikut cara menggunakannya:

---

## 1. **Install scrcpy**

* **Windows**

  1. Download release terbaru dari GitHub:
     👉 [scrcpy (GitHub)](https://github.com/Genymobile/scrcpy/releases)
  2. Extract file `.zip` ke folder.
  3. Pastikan **ADB** sudah terinstal (kalau belum, install [platform-tools Android](https://developer.android.com/tools/releases/platform-tools)).

* **Linux (Debian/Ubuntu)**

  ```bash
  sudo apt install scrcpy
  ```

* **macOS (pakai Homebrew)**

  ```bash
  brew install scrcpy
  ```

---

## 2. **Aktifkan USB Debugging di HP Android**

1. Buka **Settings > About phone**.
2. Tekan **Build number** beberapa kali sampai keluar pesan "You are now a developer".
3. Masuk ke **Developer options** dan aktifkan **USB Debugging**.

---

## 3. **Hubungkan HP ke PC**

* Sambungkan HP dengan kabel USB.
* Saat muncul pop-up *Allow USB debugging?*, pilih **Allow**.

---

## 4. **Jalankan scrcpy**

* Di terminal/command prompt, masuk ke folder `scrcpy`, lalu ketik:

  ```bash
  scrcpy
  ```
* Layar HP akan muncul di PC dan bisa dikontrol dengan mouse/keyboard. 🎉

---

## 5. **Fitur Tambahan**

* **Fullscreen**

  ```bash
  scrcpy -f
  ```
* **Batas resolusi (misal 1024p, biar ringan)**

  ```bash
  scrcpy -m 1024
  ```
* **Rekam layar sambil mirror**

  ```bash
  scrcpy --record video.mp4
  ```
* **Gunakan lewat WiFi (tanpa kabel)**

  1. Pastikan HP dan PC di jaringan yang sama.
  2. Cari IP HP:

     ```bash
     adb shell ip route
     ```
  3. Sambungkan:

     ```bash
     adb tcpip 5555
     adb connect IP_HP:5555
     scrcpy
     ```
