# ImplementasiDeteksiPola
Alfia Rohmah Safara (23422039)

```python
# Langkah 1: Clone YOLOv5 dan Install Dependencies
!rm -rf yolov5
!git clone https://github.com/ultralytics/yolov5.git
%cd yolov5
!pip install -r requirements.txt

# Langkah 2: Unggah File Gambar
from google.colab import files
from IPython.display import Image, display

# Unggah file
uploaded = files.upload()
file_name = list(uploaded.keys())[0]  # Ambil nama file yang diunggah

# Langkah 3: Jalankan Deteksi Objek
!python detect.py --source "{file_name}" --weights yolov5s.pt --conf 0.4 --save-txt

# Langkah 4: Tampilkan Hasil Deteksi
result_path = f"runs/detect/exp/{file_name}"  # Lokasi hasil deteksi
display(Image(filename=result_path))

# Langkah 5: Unduh Hasil Deteksi
from google.colab import files
files.download(result_path)
