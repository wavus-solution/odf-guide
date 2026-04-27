> **⚠️ MANDATORY FOR AI CODE GENERATION**
 > When generating HTML code or documentation with ODF, you **MUST** use these exact CDN import paths.
> **DO NOT** use local paths, alternative CDNs, or non-minified versions.

## 📦 Required CDN Imports

### CSS Import (Required)
```html
<link href="https://developer.geon.kr/js/odf/odf.css" rel="stylesheet">
```

### JavaScript Import (Required)
```html
<script type="text/javascript" src="https://developer.geon.kr/js/odf/odf.min.js"></script>
```

### ❌ Prohibited
- Local paths: `./js/odf.min.js`, `../odf/odf.css`
- Alternative CDN sources
- Non-minified: `odf.js` (use `odf.min.js`)
- Relative paths of any kind

# ODF (OpenSource Development Framework) Guide

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6+-yellow.svg)
![TypeScript](https://img.shields.io/badge/typescript-supported-blue.svg)

A comprehensive JavaScript framework for building interactive web-based GIS (Geographic Information System) applications with Korean map services integration.

## 🤖 AI Code Generation

This repository includes an AI coding skill for generating reliable ODF code. When using AI assistants (ChatGPT, Claude, etc.) to generate code from this repository:

**Important**: AI should follow the coding guidelines defined in [`skills/odf/SKILL.md`](https://github.com/wavus-solution/odf-guide/blob/main/skills/odf/SKILL.md)

### Key Principles

- Use only verified APIs from `js/odf.d.ts`
- Reference official examples in `html/` directory
- Check API documentation in `mdx/` files
- Start with `html/SAMPLES-INDEX.md` for example discovery
- Generate code based on real working examples, not assumptions

### For AI Assistants

When generating ODF code, follow these priorities:
1. Check `html/SAMPLES-INDEX.md` for relevant examples
2. Read actual example files from `html/` directory
3. Verify API signatures in `js/odf.d.ts`
4. Reference documentation in `mdx/` files
5. Combine verified patterns only - mark unverified parts with TODO comments

**Repository**: `https://github.com/wavus-solution/odf-guide.git`

---

**ODF**는 웹 기반 지리정보시스템(GIS) 애플리케이션을 쉽게 구축할 수 있는 오픈소스 개발 프레임워크입니다. 바로e맵, VWorld, Kakao 등 한국 지도 서비스와의 통합을 지원하며, OpenLayers 기반의 강력한 지도 기능을 제공합니다.

---

## 🌟 Features

### Core Capabilities
- 🗺️ **Multiple Basemap Providers** - 바로e맵, VWorld, Kakao Maps, OpenStreetMap 지원
- 📍 **Marker & Popup Management** - 마커와 팝업을 쉽게 관리
- 🎨 **Advanced Styling** - SLD(Styled Layer Descriptor) 지원 및 다양한 스타일링 옵션
- 📏 **Measurement Tools** - 거리, 면적 측정 도구
- 🎯 **Drawing & Editing** - 도형 그리기 및 편집 기능
- 📊 **Data Visualization** - 클러스터링, 차트, 히트맵 등 데이터 시각화
- 🔄 **Layer Management** - 레이어 추가, 제거, 필터링, Z-Index 관리
- 🌐 **Projection Transformation** - 좌표계 변환 지원 (EPSG:4326, EPSG:3857, EPSG:5179 등)
- ⚡ **WebGL Rendering** - 고성능 WebGL 렌더링 지원
- 📱 **Responsive Design** - 모바일 및 데스크톱 환경 모두 지원

---

## 🚀 Quick Start

### Installation

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>ODF Map Example</title>
  <!-- ODF CSS -->
  <link href="https://developer.geon.kr/js/odf/odf.css" rel="stylesheet">
  <!-- ODF JavaScript Library -->
  <script type="text/javascript" src="https://developer.geon.kr/js/odf/odf.min.js"></script>
  <style>
    #map { width: 100%; height: 550px; }
  </style>
</head>
<body>
  <div id="map" class="odf-view"></div>
  <script>
    // Map container
    var mapContainer = document.getElementById('map');

    // Map center coordinates (EPSG:5186 - Korean Central Belt)
    var coord = new odf.Coordinate(199312.9996, 551784.6924);

    // Map options
    var mapOption = {
      center: coord,
      zoom: 11,
      projection: 'EPSG:5186',
      vWorldURL: 'https://gsapi.geon.kr/map/api/vworld/wmts',
      basemap: {
        vWorld: ['vWorldBase', 'vWorldWhite', 'vWorldMidnight', 'vWorldHybrid', 'vWorldSatellite']
      }
    };

    // Create map
    var map = new odf.Map(mapContainer, mapOption);

    // Set min/max zoom levels
    map.getView().setMinZoom(8);
    map.getView().setMaxZoom(23);
  </script>
</body>
</html>
```

### Map with Basemap Control (배경지도 컨트롤)

Example: [html/mapControl/basemapControl_optimization.html](html/mapControl/basemapControl_optimization.html)

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <link href="https://developer.geon.kr/js/odf/odf.css" rel="stylesheet">
  <script type="text/javascript" src="https://developer.geon.kr/js/odf/odf.min.js"></script>
</head>
<body>
  <div id="map" class="odf-view" style="height:550px;"></div>
  <script>
    // Map container
    var mapContainer = document.getElementById('map');

    // Map center coordinates
    var coord = new odf.Coordinate(199312.9996, 551784.6924);

    // Map options with optimization
    var mapOption = {
      center: coord,
      zoom: 11,
      projection: 'EPSG:5186',
      vWorldURL: 'https://gsapi.geon.kr/map/api/vworld/wmts',
      basemap: {
        vWorld: ['vWorldBase', 'vWorldWhite', 'vWorldMidnight', 'vWorldHybrid', 'vWorldSatellite']
      },
      optimization: true // Basemap optimization
    };

    // Create map
    var map = new odf.Map(mapContainer, mapOption);

    // Create and add basemap control
    var basemapControl = new odf.BasemapControl({});
    basemapControl.setMap(map);
  </script>
</body>
</html>
```

---

## 📁 Project Structure

```
odf-guide/
├── js/
│   ├── odf.min.js              # Core library (minified)
│   └── odf.d.ts                # TypeScript definitions
├── asset/
│   └── odf.css                 # Stylesheet for ODF components
├── mdx/                        # API Documentation (39 files)
│   ├── Map.mdx                 # Map API
│   ├── Layer.mdx               # Layer API
│   ├── BasemapControl.mdx      # Basemap control
│   ├── DrawControl.mdx         # Drawing tools
│   ├── Style.mdx               # Styling API
│   └── ... (34 more files)
└── html/                       # Live Examples (180+ files)
    ├── mapControl/             # Map control examples
    ├── layerControl/           # Layer management examples
    ├── styleControl/           # Styling examples
    ├── markerControl/          # Marker examples
    ├── analysisControl/        # Analysis tools examples
    ├── sldControl/             # SLD styling examples
    ├── produceLayer/           # Layer creation examples
    ├── modifyLayer/            # Layer editing examples
    ├── featureControl/         # Feature manipulation
    ├── eventControl/           # Event handling examples
    ├── customMapControl/       # Custom controls
    ├── animation/              # Animation examples
    └── flatStyle/              # Flat styling examples
```

---

## 📚 Documentation

### API Reference

Complete API documentation is available in the `mdx/` directory:

#### Core Components
- [**Map**](mdx/Map.mdx) - Core map instance and configuration
- [**Layer**](mdx/Layer.mdx) - Layer management and operations
- [**LayerFactory**](mdx/LayerFactory.mdx) - Create various layer types (WMS, WMTS, WFS, Vector, etc.)
- [**Feature**](mdx/Feature.mdx) - Feature objects and geometry
- [**FeatureFactory**](mdx/FeatureFactory.mdx) - Feature creation utilities

#### Map Controls
- [**BasemapControl**](mdx/BasemapControl.mdx) - Switch between basemap providers
- [**ZoomControl**](mdx/ZoomControl.mdx) - Zoom in/out controls
- [**DrawControl**](mdx/DrawControl.mdx) - Drawing tools (point, line, polygon)
- [**MeasureControl**](mdx/MeasureControl.mdx) - Distance and area measurement
- [**FullScreenControl**](mdx/FullScreenControl.mdx) - Fullscreen toggle
- [**ScaleControl**](mdx/ScaleControl.mdx) - Scale bar
- [**RotationControl**](mdx/RotationControl.mdx) - Map rotation
- [**MousePositionControl**](mdx/MousePositionControl.mdx) - Mouse coordinates display
- [**OverviewMapControl**](mdx/OverviewMapControl.mdx) - Overview map
- [**BookmarkControl**](mdx/BookmarkControl.mdx) - Save and load map views
- [**DivideMapControl**](mdx/DivideMapControl.mdx) - Split screen comparison
- [**SwiperControl**](mdx/SwiperControl.mdx) - Swipe comparison
- [**PrintControl**](mdx/PrintControl.mdx) - Print/export map
- [**DownloadControl**](mdx/DownloadControl.mdx) - Download layer data
- [**ZipControl**](mdx/ZipControl.mdx) - Compress and download
- [**LayerInfoControl**](mdx/LayerInfoControl.mdx) - Layer information display

#### Styling & Visualization
- [**Style**](mdx/Style.mdx) - Style configuration
- [**StyleFactory**](mdx/StyleFactory.mdx) - Create various styles
- [**StyleFunction**](mdx/StyleFunction.mdx) - Dynamic styling functions
- [**SLD**](mdx/SLD.mdx) - Styled Layer Descriptor support
- [**ColorFactory**](mdx/ColorFactory.mdx) - Color utilities
- [**FormatFactory**](mdx/FormatFactory.mdx) - Data format handlers

#### Utilities
- [**Projection**](mdx/Projection.mdx) - Coordinate system transformation
- [**Coordinate**](mdx/Coordinate.mdx) - Coordinate utilities
- [**Extent**](mdx/Extent.mdx) - Bounding box operations
- [**Marker**](mdx/Marker.mdx) - Marker management
- [**Popup**](mdx/Popup.mdx) - Popup windows
- [**Easing**](mdx/Easing.mdx) - Animation easing functions
- [**Render**](mdx/Render.mdx) - Rendering utilities
- [**event**](mdx/event.mdx) - Event handling

---

## 💡 Examples

### 1. Map Controls

| Example | Description | Demo File |
|---------|-------------|-----------|
| Create Basic Map | 기본 지도 생성 | [createMap.html](html/mapControl/createMap.html) |
| Basemap Control | 배경지도 컨트롤 | [basemapControl_optimization.html](html/mapControl/basemapControl_optimization.html) |
| Measure Tools | 거리/면적 측정 | [measureControl.html](html/mapControl/measureControl.html) |
| Drawing Tools | 도형 그리기 | [drawControl.html](html/mapControl/drawControl.html) |
| Map Navigation | 오버뷰맵, 네비게이션 | [navigator.html](html/mapControl/navigator.html) |
| Mouse Position | 마우스 좌표 표시 | [mousePosition.html](html/mapControl/mousePosition.html) |
| Split Screen | 화면 분할 비교 | [dividedMap.html](html/mapControl/dividedMap.html) |
| Swiper Control | 스와이프 비교 | [swiperControl.html](html/mapControl/swiperControl.html) |
| Bookmark | 북마크 기능 | [bookmarkControl.html](html/mapControl/bookmarkControl.html) |
| Custom Control | 커스텀 컨트롤 | [customControl.html](html/mapControl/customControl.html) |

### 2. Layer Management

| Example | Description | Demo File |
|---------|-------------|-----------|
| Add GeoJSON Layer | GeoJSON 레이어 추가 | [layerInterChangeGeoJson.html](html/layerControl/layerInterChangeGeoJson.html) |
| Layer Filtering | 레이어 필터링 | [layerDefineQuery.html](html/layerControl/layerDefineQuery.html) |
| Spatial Filter | 공간 필터 | [layerSpatialFilter.html](html/layerControl/layerSpatialFilter.html) |
| Crop Layer | 레이어 잘라내기 | [cropPolygonLayer.html](html/layerControl/cropPolygonLayer.html) |
| Layer Z-Index | 레이어 순서 관리 | [layerZIndex.html](html/layerControl/layerZIndex.html) |
| Delete Vertex | 정점 삭제 | [deleteVertex.html](html/layerControl/deleteVertex.html) |

### 3. Layer Creation (Various Sources)

| Example | Description | Demo File |
|---------|-------------|-----------|
| WMS Layer | WMS 서비스 연결 | [wmsLayer.html](html/produceLayer/wmsLayer.html) |
| WMTS Layer | WMTS 타일 서비스 | [wmtsLayer.html](html/produceLayer/wmtsLayer.html) |
| WFS Layer | WFS 벡터 서비스 | [vWorldWFSLayer.html](html/produceLayer/vWorldWFSLayer.html) |
| VWorld TMS | VWorld 타일맵 | [vWorldTMSLayer.html](html/produceLayer/vWorldTMSLayer.html) |
| Kakao Layer | 카카오맵 레이어 | [kakaoXYZLayer.html](html/produceLayer/kakaoXYZLayer.html) |
| CSV Layer | CSV 파일 레이어 | [csvLayer.html](html/produceLayer/csvLayer.html) |
| KML Layer | KML 파일 로드 | [kmlLayer.html](html/produceLayer/kmlLayer.html) |
| GeoTIFF Layer | GeoTIFF 래스터 | [webGLGeoTiffLayer.html](html/produceLayer/webGLGeoTiffLayer.html) |
| WebGL Vector | 고성능 벡터 렌더링 | [webGLVectorLayer.html](html/produceLayer/webGLVectorLayer.html) |
| SVG Layer | SVG 레이어 | [svgLayer.html](html/produceLayer/svgLayer.html) |

### 4. Styling & Visualization

| Example | Description | Demo File |
|---------|-------------|-----------|
| Point Style | 포인트 스타일 | [simplePointStyle.html](html/styleControl/simplePointStyle.html) |
| Line Style | 라인 스타일 | [simpleLineStyle.html](html/styleControl/simpleLineStyle.html) |
| Polygon Style | 폴리곤 스타일 | [simplePolygonStyle.html](html/styleControl/simplePolygonStyle.html) |
| Label Style | 라벨 스타일 | [simpleLabelStyle.html](html/styleControl/simpleLabelStyle.html) |
| Symbol Style | 심볼 스타일 | [typeSymbolStyle.html](html/styleControl/typeSymbolStyle.html) |
| Function Style | 동적 스타일 함수 | [simpleFunctionStyle.html](html/styleControl/simpleFunctionStyle.html) |
| SLD Complex | 복잡한 SLD 스타일 | [sldComplexStyle.html](html/sldControl/sldComplexStyle.html) |
| Bar Chart | 막대 차트 스타일 | [dynamicBarChartStyle.html](html/styleControl/dynamicBarChartStyle.html) |
| Pie Chart | 파이 차트 스타일 | [pieChartStyle.html](html/styleControl/pieChartStyle.html) |
| Arrow Style | 화살표 스타일 | [arrowStyle.html](html/styleControl/arrowStyle.html) |

### 5. Analysis & Visualization

| Example | Description | Demo File |
|---------|-------------|-----------|
| Clustering | 클러스터링 | [cluster.html](html/analysisControl/cluster.html) |
| Heatmap | 히트맵 | [heatmap.html](html/analysisControl/heatmap.html) |
| Aggregate | 집계 분석 | [aggregate.html](html/analysisControl/aggregate.html) |
| Animated Cluster | 애니메이션 클러스터 | [animateCluster.html](html/analysisControl/animateCluster.html) |

### 6. Feature Operations

| Example | Description | Demo File |
|---------|-------------|-----------|
| Select Feature | 피처 선택 | [selectFeatureOnClick.html](html/featureControl/selectFeatureOnClick.html) |
| Transform Geometry | 지오메트리 변환 | [transformGeom.html](html/featureControl/transformGeom.html) |
| Feature Info | 피처 정보 조회 | [selectFeatureInfo_drawFeature.html](html/featureControl/selectFeatureInfo_drawFeature.html) |
| Split Line | 라인 분할 | [splitLine.html](html/featureControl/splitLine.html) |

### 7. Layer Editing

| Example | Description | Demo File |
|---------|-------------|-----------|
| Modify Feature | 피처 수정 | [modifyFeature.html](html/modifyLayer/modifyFeature.html) |
| Move Feature | 피처 이동 | [moveFeature.html](html/modifyLayer/moveFeature.html) |
| Insert Feature | 피처 삽입 | [insertFeature.html](html/modifyLayer/insertFeature.html) |
| Delete Feature | 피처 삭제 | [deleteFeature.html](html/modifyLayer/deleteFeature.html) |
| Layer Modify | 레이어 수정 | [layerModify.html](html/modifyLayer/layerModify.html) |

### 8. Markers & Popups

| Example | Description | Demo File |
|---------|-------------|-----------|
| Basic Marker | 기본 마커 | [marker.html](html/markerControl/marker.html) |
| Custom Marker | 커스텀 마커 | [customMarker.html](html/markerControl/customMarker.html) |
| Mouse Tooltip | 마우스 툴팁 | [mouseTooltip.html](html/markerControl/mouseTooltip.html) |

### 9. Events

| Example | Description | Demo File |
|---------|-------------|-----------|
| Basic Events | 기본 이벤트 | [basicEvent.html](html/eventControl/basicEvent.html) |
| Map Events | 맵 이벤트 | [mapEvent.html](html/eventControl/mapEvent.html) |
| Layer Events | 레이어 이벤트 | [layerEvent.html](html/eventControl/layerEvent.html) |

### 10. Animations

| Example | Description | Demo File |
|---------|-------------|-----------|
| Follow Line Animation | 경로 따라가기 애니메이션 | [followLineAnimation.html](html/animation/followLineAnimation.html) |
| Flight Animation | 비행 애니메이션 | [flightAnimation.html](html/animation/flightAnimation.html) |
| Wave Animation | 파동 애니메이션 | [waveAnimation.html](html/animation/waveAnimation.html) |

---

## 🔧 TypeScript Support

ODF provides TypeScript definitions for better IDE support and type safety.

```typescript
import type { Map, Layer, BasemapControl } from './js/odf';

const map: Map = new odf.Map({
  target: 'map',
  view: {
    center: [127.0, 37.5],
    zoom: 10
  }
});
```

TypeScript definitions are available at: `js/odf.d.ts`

---

## 🌐 Supported Basemap Providers

### 바로e맵 (Baro E-Map)
- 기본 지도 (eMapBasic)
- 색각 지도 (eMapColor)
- 큰글씨 지도 (eMapLowV)
- 백지도 (eMapWhite)
- 영어 지도 (eMapEnglish)
- 중국어 지도 (eMapChinese)
- 일본어 지도 (eMapJapanese)
- 위성 지도 (eMapSatellite)
- 영상 지도 (eMapAIR)

### VWorld (브이월드)
- 기본 지도 (vWorldBase)
- 회색 지도 (vWorldWhite)
- 야간 지도 (vWorldMidnight)
- 하이브리드 지도 (vWorldHybrid)
- 위성 지도 (vWorldSatellite)

### Kakao Maps (카카오맵)
- 기본 지도 (kakaoBase)
- 스카이뷰 (kakaoSkyview)

### OpenStreetMap
- OSM 기본 지도

---

## 🎯 Use Cases

ODF is ideal for:

- **공공 데이터 시각화** - Visualizing public sector geographic data
- **재난 관리 시스템** - Disaster management and emergency response systems
- **부동산 플랫폼** - Real estate and property mapping applications
- **물류/배송 관리** - Logistics and delivery route planning
- **스마트시티 대시보드** - Smart city monitoring dashboards
- **환경 모니터링** - Environmental data monitoring and analysis
- **교통 분석** - Traffic analysis and transportation planning
- **관광 안내 시스템** - Tourism information systems

---

## 🔑 Keywords

JavaScript GIS, Web Mapping, WebGIS, 바로e맵, VWorld, Kakao Maps, Korean Map API, OpenLayers, Leaflet Alternative, 지도 라이브러리, 한국 지도, WebGIS Framework, GIS JavaScript Library, 오픈레이어스, 웹 지도, 공간정보, Geospatial, Cartography, Map Visualization, SLD, WMS, WMTS, WFS, Vector Tiles, GeoJSON, KML

---

## 📄 License

[Specify your license here - e.g., MIT, Apache 2.0, etc.]

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

Feel free to check the [issues page](../../issues) if you want to contribute.

---

## 📧 Contact

For questions or support, please open an issue on GitHub.

---

## 🙏 Acknowledgments

Built on top of [OpenLayers](https://openlayers.org/) with additional features and Korean map service integrations.

---

**Made with ❤️ for the Korean GIS community**
