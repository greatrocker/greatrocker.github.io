AI CCTV 智慧工廠監控系統 (Manufacturing Monitoring System)
本專案利用電腦視覺技術針對 PCB 生產線進行即時監控與自動化分析。透過整合 YOLO 辨識模型與工業控制協定，實現製程效率追蹤與異常告警。

核心功能
多站點監控支援：
即時影像辨識：
使用 YOLOv8/v10 模型進行工件辨識與製程動作追蹤。
自定義 ROI (Region of Interest) 區域，精準鎖定檢測範圍。
硬體連聯動與告警：
透過 Modbus TCP 協定即時控制工業警示燈 (Warning Lamp)。
當辨識到異常動作或錯誤流程時，立即觸發燈號。
數據統計與整合：
自動班別判斷：根據當前時間自動區分日班與夜班。
本地日誌記錄：將辨識結果與統計數據存儲為 CSV 檔案。
Web API 整合：即時將生產數據推送至後端管理系統。
技術棧 (Tech Stack)
語言: Python 3.x
影像處理: OpenCV, FFmpeg (RTSP Stream)
深度學習: PyTorch, Ultralytics YOLO (v8/v10)
工業通訊: Modbus TCP (Raw Client)
數據處理: NumPy, pytz, requests
專案結構 (部分)
DES_temporarily_backup.py: DES 站點監控邏輯。
ENIG_backup.py: ENIG 站點監控邏輯。
VRS_backup.py: VRS 站點檢修動作監控。
warning_lamp.py: Modbus TCP 控制模組。
使用說明
確保已安裝相關依賴：pip install opencv-python ultralytics torch requests ffmpeg-python pytz
配置 RTSP 攝影機地址。
執行對應站點的指令碼，例如：python DES_temporarily_backup.py
