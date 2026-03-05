# Audio-Signal-Denoising-FIR 🔊

## 🇬🇧 English

A Python-based Digital Signal Processing project that removes high-frequency
Gaussian noise from audio signals using FIR (Finite Impulse Response) digital
filters with a Hamming window, developed as a Digital Signal Processing course
project at Ho Chi Minh City University of Science.

### Overview

This project demonstrates a complete audio denoising pipeline: loading a real
WAV audio file, artificially adding high-frequency Gaussian noise (above 5000 Hz),
designing an FIR lowpass filter windowed with a Hamming function, applying the
filter to recover the clean signal, and comparing time-domain and
frequency-domain (FFT) results before and after filtering.

### Signal Processing Pipeline
| Step | Description |
|---|---|
| 1 | Load audio signal from `smallgirl.wav` (mono, first channel) |
| 2 | Generate Gaussian noise (σ = 0.02), shaped by highpass filter at 5000 Hz |
| 3 | Add noise to original signal |
| 4 | Design FIR Lowpass filter using Hamming window |
| 5 | Apply filter via convolution (`np.convolve`) |
| 6 | Analyze FFT spectrum before and after filtering |
| 7 | Export results to `noisy.wav` and `filtered.wav` |

### Filter Theory
| Filter | Impulse Response Formula |
|---|---|
| FIR Lowpass | h(n) = wc/π for n=0; sin(wc·n)/(π·n) for n≠0 |
| FIR Highpass | h(n) = 1−wc/π for n=0; −sin(wc·n)/(π·n) for n≠0 |
| Hamming Window | w(n) = 0.54 − 0.46·cos(2πn/(N−1)) for 0≤n≤N−1 |

### Improvements over Original MATLAB Code
- Ported from MATLAB (`audioread`) to **Python** (`scipy.io.wavfile`)
- Input changed from `.mp3` to `.wav` format for better compatibility
- Added **highpass-filtered Gaussian noise** for realistic high-frequency interference
- Added **output file export** — saves `noisy.wav` and `filtered.wav` for audible comparison
- Full FFT visualization before and after each processing stage

### Technologies
- Python — NumPy, SciPy (`wavfile`, `signal`), Matplotlib
- Filter design: custom FIR coefficients + Hamming window + `np.convolve`

### How to Run
```bash
pip install numpy scipy matplotlib
python project4.py
```

---

## 🇻🇳 Tiếng Việt

Đồ án Xử lý Tín hiệu Số sử dụng Python để loại bỏ nhiễu Gaussian tần số
cao khỏi tín hiệu âm thanh bằng bộ lọc FIR (Finite Impulse Response) kết
hợp cửa sổ Hamming, thực hiện trong khuôn khổ môn Xử lý Tín hiệu Số tại
Trường Đại học Khoa học Tự nhiên TP.HCM.

### Tổng quan

Đồ án minh họa toàn bộ quy trình khử nhiễu âm thanh: đọc file WAV thực
tế, tạo nhiễu Gaussian tần số cao (trên 5000 Hz), thiết kế bộ lọc FIR
thông thấp với cửa sổ Hamming, áp dụng bộ lọc để phục hồi tín hiệu sạch,
và so sánh kết quả trên miền thời gian và miền tần số (FFT).

### Chuỗi xử lý tín hiệu
| Bước | Mô tả |
|---|---|
| 1 | Đọc tín hiệu âm thanh từ `smallgirl.wav` (mono, kênh đầu tiên) |
| 2 | Tạo nhiễu Gaussian (σ = 0.02), lọc qua bộ lọc thông cao tại 5000 Hz |
| 3 | Cộng nhiễu vào tín hiệu gốc |
| 4 | Thiết kế bộ lọc FIR thông thấp với cửa sổ Hamming |
| 5 | Áp dụng bộ lọc bằng tích chập (`np.convolve`) |
| 6 | Phân tích phổ FFT trước và sau lọc |
| 7 | Xuất kết quả ra `noisy.wav` và `filtered.wav` |

### Lý thuyết bộ lọc
| Bộ lọc | Công thức đáp ứng xung |
|---|---|
| FIR thông thấp | h(n) = wc/π khi n=0; sin(wc·n)/(π·n) khi n≠0 |
| FIR thông cao | h(n) = 1−wc/π khi n=0; −sin(wc·n)/(π·n) khi n≠0 |
| Cửa sổ Hamming | w(n) = 0.54 − 0.46·cos(2πn/(N−1)) với 0≤n≤N−1 |

### Cải tiến so với code MATLAB gốc
- Chuyển từ MATLAB (`audioread`) sang **Python** (`scipy.io.wavfile`)
- Đầu vào từ `.mp3` sang `.wav` để tương thích tốt hơn
- Thêm **nhiễu Gaussian lọc thông cao** để mô phỏng nhiễu tần số cao thực tế
- Thêm **xuất file âm thanh** — lưu `noisy.wav` và `filtered.wav` để nghe so sánh
- Trực quan hóa FFT đầy đủ trước và sau từng bước xử lý

### Công nghệ
- Python — NumPy, SciPy (`wavfile`, `signal`), Matplotlib
- Thiết kế bộ lọc: hệ số FIR tự thiết kế + cửa sổ Hamming + `np.convolve`

### Cách chạy
```bash
pip install numpy scipy matplotlib
python project4.py
```
