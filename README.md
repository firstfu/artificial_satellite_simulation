# Advanced Artificial Satellite Simulation System | 進階人造衛星模擬系統

<div align="center">
  <img src="https://raw.githubusercontent.com/username/artificial_satellite_simulation/main/screenshots/preview.png" alt="Simulation System Preview" width="800">
</div>

[English](#english) | [繁體中文](#繁體中文)

---

<a name="english"></a>

## English

### Project Overview

This is an artificial satellite orbit simulation system developed with Three.js, providing an intuitive and interactive 3D visualization environment to demonstrate how various types of artificial satellites orbit the Earth. The system runs entirely in-browser without requiring any additional software installation.

### Key Features

- **Multiple Satellite Types**: Support for communication, weather, navigation, Earth observation, and military satellites
- **Diverse Orbit Heights**: Including Low Earth Orbit (LEO), Medium Earth Orbit (MEO), Geostationary Orbit (GEO), and High Earth Orbit (HEO)
- **Realistic Earth Model**: High-resolution Earth surface textures with cloud layers, atmosphere effects, and lighting
- **Day-Night Cycle Simulation**: Adjustable day-night cycle to observe solar effects on satellites
- **Satellite Communication Visualization**: Simulation of signal transmission between satellites and Earth
- **Time Control System**: Adjustable simulation time flow rate to speed up or slow down the simulation process
- **Detailed Satellite Information**: Display of technical parameters such as orbit height, period, and velocity for each satellite
- **Comprehensive Camera Control**: Freedom to rotate and zoom to view satellites and Earth

### User Guide

#### Satellite Controls

- **Add Satellite**: Select satellite type and orbit height, then click the "Add Satellite" button
- **Remove Satellite**: Click the "Remove Satellite" button to delete the last added satellite
- **Display Orbit Data**: Toggle to show detailed orbit and technical parameters for satellites
- **Satellite Speed Adjustment**: Use the slider to adjust the movement speed of all satellites

#### Environment Controls

- **Earth Rotation**: Pause or resume Earth's rotation
- **Celestial Body Display**: Choose to show or hide the Moon, Sun, stars, and cloud layer
- **Rotation Speed**: Adjust Earth's rotation speed

#### Visual Effects

- **Orbit Lines**: Show or hide satellite orbit paths
- **Atmosphere**: Show or hide Earth's atmospheric effects
- **Grid**: Enable coordinate grid for observation assistance
- **Camera Distance**: Adjust the viewing distance

#### Time Controls

- **Simulation Time**: Display of current time within the simulation system
- **Time Flow Rate**: Speed up or slow down the simulation time flow
- **Day-Night Cycle**: Adjust the Sun's position to change lighting angles

### Technical Implementation

This simulation system is implemented using the following technologies:

- **Three.js**: For creating and rendering 3D scenes
- **JavaScript ES6+**: For implementing satellite movement and orbit calculations
- **HTML5 & CSS3**: For building the user interface and control panels
- **Web Standards**: To ensure perfect operation in modern browsers

### System Requirements

- Modern browser with WebGL support (Chrome, Firefox, Safari, Edge, etc.)
- Desktop device recommended for the best experience
- Dedicated graphics card recommended for smooth 3D rendering

### Getting Started

1. Clone or download the project to your local machine
2. Open the `index.html` file with a modern browser
3. Or visit the online demo version: [https://username.github.io/artificial_satellite_simulation/](https://username.github.io/artificial_satellite_simulation/)

---

## Technical Notes and Implementation Details

### Satellite Orbit Calculation

The system uses a simplified Keplerian orbit calculation method, computing orbital velocity based on orbit height:

```javascript
// Calculate orbital velocity (based on orbit radius)
const baseSpeed = 0.005;
const speedFactor = Math.sqrt(7 / orbitRadius); // Simplified from Kepler's Third Law
const rotationSpeed = baseSpeed * speedFactor;
```

### Earth-Sun-Moon System

The system simulates the relative motion of the Earth-Sun-Moon system, with day-night cycles and moon phase changes based on real astronomical phenomena:

```javascript
// Update sun and moon positions (based on day-night cycle)
function updateCelestialBodies() {
  // Move the sun
  const sunAngle = dayCyclePosition * Math.PI * 2;
  const sunDistance = 100;
  sun.position.x = Math.cos(sunAngle) * sunDistance;
  sun.position.z = Math.sin(sunAngle) * sunDistance;

  // Move the moon
  const moonAngle = simTime * 0.00001 + Math.PI;
  moonOrbit.rotation.y = moonAngle;
}
```

---

<a name="繁體中文"></a>

## 繁體中文

### 專案簡介

這是一個基於 Three.js 開發的人造衛星軌道模擬系統，提供了直觀且互動性強的 3D 視覺化環境，用於模擬各種類型人造衛星如何環繞地球運行。系統完全在瀏覽器中運行，無需安裝任何額外軟體。

### 功能特色

- **多種衛星類型**：支援通訊衛星、氣象衛星、導航衛星、地球觀測衛星和軍事衛星等不同類型
- **多樣化軌道高度**：包含低軌道(LEO)、中軌道(MEO)、地球同步軌道(GEO)和高軌道(HEO)
- **逼真的地球模型**：高解析度的地球表面紋理，包含雲層、大氣層和光照效果
- **日夜循環模擬**：可調節的日夜循環，觀察太陽光對衛星的影響
- **衛星通訊視覺化**：模擬衛星與地球間的通訊信號傳輸
- **時間控制系統**：可調節模擬時間流速，加速或減慢模擬過程
- **詳細的衛星資訊**：顯示每個衛星的軌道高度、週期和速度等技術參數
- **全方位相機控制**：可自由旋轉、縮放查看衛星和地球

### 使用指南

#### 衛星控制

- **新增衛星**：選擇衛星類型和軌道高度，點擊「新增衛星」按鈕
- **移除衛星**：點擊「移除衛星」按鈕刪除最後添加的衛星
- **顯示軌道資料**：切換顯示衛星的詳細軌道和技術參數
- **衛星速度調整**：使用滑桿調整所有衛星的運行速度

#### 環境控制

- **地球旋轉**：可暫停或繼續地球自轉
- **天體顯示**：可選擇顯示或隱藏月球、太陽、星空和雲層
- **自轉速度**：調整地球自轉速度

#### 視覺效果

- **軌道線**：顯示或隱藏衛星軌道路徑
- **大氣層**：顯示或隱藏地球大氣層效果
- **座標網格**：開啟座標網格輔助觀察
- **相機距離**：調整觀察視角的遠近

#### 時間控制

- **模擬時間**：顯示當前模擬系統內的時間
- **時間流速**：可加快或減慢模擬時間流速
- **日夜循環**：調整太陽位置，改變日照角度

### 技術實現

本模擬系統採用以下技術實現：

- **Three.js**：用於創建和渲染 3D 場景
- **JavaScript ES6+**：實現衛星運動和軌道計算
- **HTML5 & CSS3**：構建用戶界面和控制面板
- **Web 標準**：確保在現代瀏覽器中完美運行

### 系統需求

- 支援 WebGL 的現代瀏覽器 (Chrome, Firefox, Safari, Edge 等)
- 建議使用桌面設備以獲得最佳體驗
- 推薦配備獨立顯卡以實現流暢的 3D 渲染

### 開始使用

1. 克隆或下載本專案到本地
2. 使用現代瀏覽器開啟 `index.html` 文件
3. 或直接訪問線上演示版本: [https://username.github.io/artificial_satellite_simulation/](https://username.github.io/artificial_satellite_simulation/)

---

## 技術說明與實作細節

### 衛星軌道計算

系統採用簡化的開普勒軌道計算法則，根據軌道高度計算相應的軌道速度：

```javascript
// 計算軌道速度 (基於軌道半徑)
const baseSpeed = 0.005;
const speedFactor = Math.sqrt(7 / orbitRadius); // 基於開普勒第三定律的簡化
const rotationSpeed = baseSpeed * speedFactor;
```

### 地球-太陽-月球系統

系統模擬了地球-太陽-月球系統的相對運動，日夜循環和月相變化均基於真實天文現象建立：

```javascript
// 更新太陽和月球位置（基於日夜循環）
function updateCelestialBodies() {
  // 移動太陽
  const sunAngle = dayCyclePosition * Math.PI * 2;
  const sunDistance = 100;
  sun.position.x = Math.cos(sunAngle) * sunDistance;
  sun.position.z = Math.sin(sunAngle) * sunDistance;

  // 移動月球
  const moonAngle = simTime * 0.00001 + Math.PI;
  moonOrbit.rotation.y = moonAngle;
}
```

---

### License | 授權協議

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

本專案採用 MIT 授權協議 - 詳情請查閱 [LICENSE](LICENSE) 文件
