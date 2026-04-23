# ODF 지도 샘플 예제 인덱스

이 문서는 ODF(OpenSource Developer Framework) 지도 라이브러리의 샘플 예제 목록입니다.
---

## 목차

1. [지도제어](#1-지도제어)
2. [화면 제어](#2-화면-제어)
3. [사용자 정의 컨트롤](#3-사용자-정의-컨트롤)
4. [레이어 생성](#4-레이어-생성)
5. [레이어 제어](#5-레이어-제어)
6. [레이어 편집](#6-레이어-편집)
7. [WFS 단일/복합 스타일](#7-wfs-단일복합-스타일)
8. [WFS 동적스타일](#8-wfs-동적스타일)
9. [WMS 스타일(SLD)](#9-wms-스타일sld)
10. [Flat 스타일 / 스타일 표현식](#10-flat-스타일--스타일-표현식)
11. [애니메이션](#11-애니메이션)
12. [오버레이](#12-오버레이)
13. [이벤트](#13-이벤트)
14. [분석 레이어](#14-분석-레이어)

---

## 1. 지도제어

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 프로젝트 기본 설정 | 프로젝트 기본 설정 값 셋팅 | `mapControl/odfInit.html` |
| 지도생성 | 지도를 생성 기능 제공 | `mapControl/createMap.html` |
| 배경지도만 키보드로 이동 | 키보드 화살표키를 누르면 레이어는 이동되지않고 배경지도를 10픽셀씩 이동하는 기능 제공 | `mapControl/keyboardMoveMap.html` |
| 지도 좌표계 변경 | 지도 좌표계 변경 기능 제공 | `mapControl/changeMapProjection.html` |
| 배경지도 설정 | 배경지도 설정 기능 제공 | `mapControl/basemapControl.html` |
| 배경지도 최적화 | 배경지도 변경시 지도 좌표계 변경하여 조금 더 선명한 배경지도를 이용 | `mapControl/basemapControl_optimization.html` |
| 배경지도 최적화 전/후 비교 | 배경지도 좌표계 최적화를 통한 해상도 개선 비교 | `mapControl/basemapControl_optimization_compare.html` |
| 사용자 지정 배경지도 | 사용자 정의 배경지도 그룹/레이어 관리 기능 제공 | `mapControl/customizeBasemap.html` |
| 사용자 지정 배경지도(webGl 벡터타일 레이어) | 사용자 정의 배경지도 그룹/레이어 관리 기능 제공 | `mapControl/customizeBasemap_vectorTile.html` |
| 구글 지도에 ODF 레이어 추가 | 구글 지도에 ODF 레이어를 추가하여 사용 | `mapControl/customizeBasemap_google.html` |
| 네이버 지도에 ODF 레이어 추가 | 네이버 지도에 ODF 레이어를 추가하여 사용 | `mapControl/customizeBasemap_naver.html` |
| 카카오 지도에 ODF 레이어 추가 | 카카오 지도에 ODF 레이어를 추가하여 사용 | `mapControl/customizeBasemap_kakao.html` |
| 축척 | 지도의 축척정보 조회 기능 제공 | `mapControl/scaleControl.html` |
| 네비게이션 | 지도의  네비게이션(이전/다음 화면) 기능 제공 | `mapControl/navigator.html` |
| 인덱스맵 | 지도를 한 눈에 볼 수 있는 인덱스맵 제공  | `mapControl/indexmapControl.html` |
| 지도회전 | 지도 회전 기능 제공 | `mapControl/rotationControl.html` |
| 그리기 도구 | 점, 선, 면, 곡선, 다각형, 사각형, 버퍼 그리기 도구 기능 제공 | `mapControl/drawControl.html` |
| 측정 도구 | 면적/거리/측정 기능 제공 | `mapControl/measureControl.html` |
| 그리기 도구/측정 도구 복합 스타일 | 하나의 도형에 본체 스타일과 버텍스 스타일을 함께 적용 | `mapControl/drawControlCompositeStyle.html` |
| 지도 출력/다운로드 | 지도 출력 및 다운로드(PDF/이미지) 기능 제공 | `mapControl/capture&print.html` |
| 마우스 좌표 표시/전체화면 | 사용자의 마우스 좌표 표출 기능과 전체화면 기능 제공 | `mapControl/mousePosition.html` |
| 지도 드래그/휠 막기 | 지도를 생성하고 배경지도 설정을 제공하고
					 * 있습니다.  | `mapControl/drag&wheel.html` |

## 2. 화면 제어

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 스와이퍼 | 지도스와이퍼 기능 제공 | `mapControl/swiperControl.html` |
| 사용자 정의 스와이퍼 | 사용자 정의대로 스와이퍼를 생성하는 기능 제공 | `mapControl/customizeSwiperControl.html` |
| 분할지도 | 2/3/4 분할지도 기능 제공 | `mapControl/dividedMap.html` |
| 분할지도 상세 | 메인지도의 컨트롤/레이어 복사하여 분할된 지도에 적용하는 기능 제공 | `mapControl/dividedMap_detailSet.html` |
| 사용자 정의 2분할 지도 | 사용자 정의대로 2분할 지도를 생성하는 기능 제공 | `mapControl/dualDividedMap.html` |
| 사용자 정의 4분할 지도 | 사용자 정의대로 4분할 지도를 생성하는 기능 제공 | `mapControl/quadDividedMap.html` |

## 3. 사용자 정의 컨트롤

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 컨트롤 순서 변경 | 사용자 정의대로 컨트롤 순서 변경하는 기능 제공 | `mapControl/customControlOrder.html` |
| 사용자 정의 단일 컨트롤 | 사용자 정의대로 단일 컨트롤을 생성하는 기능 제공   | `mapControl/customControl.html` |
| 사용자 정의 서브 그룹 컨트롤 | 사용자 정의대로 서브 그룹 컨트롤 생성하는 기능 제공 | `mapControl/customSubGroupControl.html` |
| 분할지도-사용자정의 컨트롤 추가 | 분할지도에 사용자정의 컨트롤 추가 기능 제공 | `mapControl/customControlDIvidmap.html` |

## 4. 레이어 생성

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| wfs 레이어 생성(geoserver 타입) | wfs 레이어 생성 기능 제공 | `produceLayer/wfsLayer.html` |
| wfs 레이어 생성(geoserver 타입) -attribution 적용 | wfs 레이어 생성시 attribution 정의 | `produceLayer/wfsLayer_attributions.html` |
| wms 레이어 생성(geoserver 타입) | wms 레이어 생성 기능 제공 | `produceLayer/wmsLayer.html` |
| wmts 레이어 생성(geoserver 타입) | wmts 레이어 생성 기능 제공 | `produceLayer/wmtsLayer.html` |
| 빈 벡터 레이어 생성 | 빈 벡터 레이어 생성 기능 제공 | `produceLayer/emptyLayer.html` |
| geojson 레이어 생성 | geojson 형식의 데이터로 레이어 생성 기능 제공 | `produceLayer/geojsonLayer.html` |
| shape 파일로 Layer 생성(미리보기) | shape 파일로 Layer 생성(미리보기) 기능 제공 | `produceLayer/drawLayerToFile.html` |
| KML 레이어 생성 | KML 형식의 데이터로 도형을 생성하는 기능 제공 | `produceLayer/kmlLayer.html` |
| CSV 레이어 생성 | CSV 형식의 데이터로 도형을 생성하는 기능 제공 | `produceLayer/csvLayer.html` |
| 국가공간정보 포털 WMS 레이어 생성(api 타입) | 국가공간정보 포털 api를 이용하여 WMS 레이어 생성 기능 제공 | `produceLayer/nsidWMSLayer.html` |
| vWorld WMS 레이어 생성(api 타입) | vWorld api를 이용하여 WMS 레이어 생성 기능 제공 | `produceLayer/vWorldWMSLayer.html` |
| vWorld WFS 레이어 생성(api 타입) | vWorld api를 이용하여  WFS 레이어 생성 기능 제공 | `produceLayer/vWorldWFSLayer.html` |
| kakao xyz 레이어 생성(api 타입) | kakao api를 이용하여 xyz 레이어 생성 기능 제공 | `produceLayer/kakaoXYZLayer.html` |
| kakao 로드뷰 레이어 생성(api 타입) | kakao api를 이용하여 로드뷰 레이어 생성 기능 제공 | `produceLayer/kakaoRoadview.html` |
| 네이버 로드뷰 레이어 생성(api 타입) | 네이버 api를 이용하여 로드뷰 레이어 생성 기능 제공 | `produceLayer/naverRoadview.html` |
| vWorld TMS 레이어 생성(api 타입) | vWorld api를 이용하여 tms 레이어 생성 기능 제공 | `produceLayer/vWorldTMSLayer.html` |
| 이미지 레이어 생성 | 이미지 레이어 생성 기능 제공 | `produceLayer/ImageLayer.html` |
| 타일 디버그 레이어 생성 | 타일 디버그 레이어 생성 기능 제공 | `produceLayer/tileDebugLayer.html` |
| 벡터 타일 레이어 (pbf) | vectorTile 레이어 생성 기능 | `produceLayer/vectorTileLayer.html` |
| 벡터 레이어 생성 속도 비교(canvas vs webGL) | 벡터 레이어 생성 속도 비교(canvas vs webGL) | `produceLayer/webGLVectorLayer_performance.html` |
| webGL 벡터(wfs) 레이어 생성 | webGL 벡터(wfs) 레이어 생성 기능 | `produceLayer/webGLVectorLayer.html` |
| webGL 벡터(geojson) 레이어 생성 | webGL 벡터(geojson) 레이어 생성 기능 | `produceLayer/webGLVectorLayer_geojson.html` |
| webGL 타일(wms) 레이어 생성 | webGL 타일(wms) 레이어 생성 기능 | `produceLayer/webGLTileLayer.html` |
| webGL 타일(wmts) 레이어 생성 | webGL 타일(wmts) 레이어 생성 기능 | `produceLayer/webGLTileLayer_wmts.html` |
| webGL 벡터 타일(pbf) 레이어 생성 | webGL 타일(pbf) 레이어 생성 기능 | `produceLayer/webGLVectorTileLayer.html` |
| webGL GeoTiff 레이어 생성 | webGL GeoTiff 레이어 생성 기능 | `produceLayer/webGLGeoTiffLayer.html` |
| svg 레이어 생성 | svg 레이어 생성 기능 | `produceLayer/svgLayer.html` |
| 카토그램 제작(svg 레이어 생성 응용) | svg 레이어 생성 기능을 이용하여 카토그램 제작 | `produceLayer/svgLayer_cartogram.html` |

## 5. 레이어 제어

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 레이어 on/off | 레이어를 지도에서 on/off  | `layerControl/layerSwitch.html` |
| 레이어 Z-Index(순서) 설정 | 레이어의 순서를 설정 | `layerControl/layerZIndex.html` |
| 레이어 가시 범위 설정 | 레이어의 가시 범위 설정 | `layerControl/layerSetZoom.html` |
| 레이어 필터 | 레이어에 필터를 적용하여 필터링 된 레이어 정보 표출 | `layerControl/layerDefineQuery.html` |
| 레이어 공간검색 | 영역을 선택하여 레이어 필터 | `layerControl/layerSpatialFilter.html` |
| 레이어 Extent | 레이어 영역에 맞게 지도 영역 이동 | `layerControl/layerExtent.html` |
| Layer와GeoJson 상호변환 | Layer와 GeoJson 상호변환 기능 제공 | `layerControl/layerInterChangeGeoJson.html` |
| X, Y 좌표변환 | 좌표값(X,Y)을 다른 좌표계 값으로 변환 기능 제공 | `layerControl/transformXY.html` |
| Extent 좌표변환 | Extent의 좌표를 다른 좌표계 값으로 변환 기능 제공 | `layerControl/transformExtent.html` |
| 라인으로 다각형 분할 | 사용자가 그린 선으로 다각형을 분할 | `layerControl/SplitFeature.html` |
| 영역으로 버텍스 다중 삭제 | 사용자가영역으로(다각형) 피쳐 버텍스 다중 삭제 | `layerControl/deleteVertex.html` |
| 레이어 원형으로 자르기 | 레이어 원형으로 자르기 기능 제공 | `layerControl/cropCircleLayer.html` |
| 레이어 다각형으로 자르기 | 레이어 다각형으로 자르기 기능 제공 | `layerControl/cropPolygonLayer.html` |
| 레이어 멀티-다각형으로 자르기 | 레이어 멀티-다각형으로 자르기 기능 제공 | `layerControl/cropMultiPolygonLayer.html` |

## 6. 레이어 편집

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 피처를 그려서 레이어에 추가 | 피처를 그려서 레이어에 추가하여 서버 적용 기능 제공 | `modifyLayer/insertFeature.html` |
| 선택 피처 삭제 | 선택한 피처를 삭제하여 서버 적용 기능 제공 | `modifyLayer/deleteFeature.html` |
| 드래그로 레이어/피처 이동/회전/크기조절 | 드래그로 레이어/피처 이동/회전/크기조절하여 서버 적용 기능 제공 | `modifyLayer/dragTranslate.html` |
| 드래그로 레이어 이동 | 드래그로 레이어 이동하여 서버 적용 기능 제공 | `modifyLayer/moveLayer.html` |
| 드래그로 피처 편집 | 드래그로 피처 편집하여 서버적용 기능 제공 | `modifyLayer/modifyFeature.html` |
| 드래그로 피처 이동 | 드래그로 피처 이동하여 서버적용 기능 제공 | `modifyLayer/moveFeature.html` |
| 드래그로 피처 크기 조절 및 회전 | 드래그로 피처 크기 조절 및 회전하여 서버적용 기능 제공 | `modifyLayer/transformFeature.html` |
| 스냅 | 레이어를 편집/피처 추가 기능을 스냅과 함께 제공 | `modifyLayer/modifyLayer_Snap.html` |

## 7. WFS 단일/복합 스타일

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 단일 점 스타일 | 단일 점 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simplePointStyle.html` |
| 단일 타원 스타일 | 단일 타원 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simplePointStyle_ellipse.html` |
| 단일 심볼 스타일 | 단일 심볼 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simpleSymbolStyle.html` |
| 사용자 정의 심볼 스타일 | 사용자 정의 심볼 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simpleSymbolStyle_customImage.html` |
| 정다각형(regular shapes) 스타일 | 정다각형(regular shapes) 스타일 생성하여 벡터레이어에 적용 | `styleControl/simpleRegularShape.html` |
| 단일 선 스타일 | 단일 선 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simpleLineStyle.html` |
| 단일 면 스타일 | 단일 면 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simplePolygonStyle.html` |
| 단일 면 스타일(라벨 위치 조정) | 단일 면 라벨 스타일 위지 조정 | `styleControl/simplePolygonStyle_customPosition.html` |
| 단일 라벨 스타일 | 단일 라벨 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simpleLabelStyle.html` |
| 단일 라벨 스타일(서식 지정) | 단일 라벨 스타일을 서식을 지정하여 생성, 벡터 레이어에 적용 | `styleControl/simpleLabelStyle_richText.html` |
| 단일 패턴 스타일 | 단일 패턴 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simplePatternStyle.html` |
| 파이 차트 스타일 | 파이 차트 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/pieChartStyle.html` |
| 막대 차트 스타일 | 막대 차트 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/barChartStyle.html` |
| 복합스타일 | 복합 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/complexStyle.html` |
| 스타일 객체 ↔ JSON | 스타일 객체를 JSON 형태로 변경 | `styleControl/simpleStyleCvt2JSON.html` |
| (복합스타일) 도형 버텍스 표현 스타일 | 도형 버텍스 표현 스타일 | `styleControl/vertexStyle.html` |

## 8. WFS 동적스타일

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 동적 스타일 | 동적 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/simpleFunctionStyle.html` |
| 동적 파이 차트 스타일 | 동적 파이 차트 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/dynamicPieChartStyle.html` |
| 동적 막대 차트 스타일(가로) | 동적 막대 차트 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/dynamicBarChartStyle_horizon.html` |
| 동적 막대 차트 스타일(세로) | 동적 막대 차트 스타일을 생성하여 벡터 레이어에 적용 | `styleControl/dynamicBarChartStyle.html` |
| 유형별 스타일(점-원형) | 벡터레이어에 유형별 스타일 적용(점-원형) | `styleControl/typeStyle.html` |
| 유형별 스타일(점-심볼) | 벡터레이어에 유형별 스타일 적용(점-심볼) | `styleControl/typeSymbolStyle.html` |
| 범위별 스타일 | 벡터레이어에 범위별로 스타일 적용 | `styleControl/rangeStyle.html` |
| 색 추출기 | 색 추출기를 이용하여 색 생성 | `styleControl/colorFactory.html` |
| 범례용 Element | 벡터레이어 범례용 Element 생성 | `styleControl/createLegendElement.html` |
| 동적스타일 ↔ JSON | 동적스타일객체를 JSON 형태로 변경 | `styleControl/functionStyleCvt2JSON.html` |
| 화살표 스타일 | 방향을 스타일로 표현 | `styleControl/arrowStyle.html` |

## 9. WMS 스타일(SLD)

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 점 스타일 | WMS 점 스타일 적용 | `sldControl/pointStyle.html` |
| 심볼 스타일 | WMS 심볼 스타일 적용 | `sldControl/symbolStyle.html` |
| 선 스타일 | WMS 선 스타일 적용 | `sldControl/lineStyle.html` |
| 면 스타일 | WMS 면 스타일 적용 | `sldControl/polygonStyle.html` |
| 라벨 스타일 | WMS 라벨 스타일 적용 | `sldControl/labelStyle.html` |
| 복합 스타일 | WMS 복합 스타일(선스타일+라벨스타일) 적용 | `sldControl/sldComplexStyle.html` |
| 유형별 스타일 | WMS 유형별 스타일 적용 | `sldControl/sldTypeStyle.html` |
| SLD 적용 Scale | SLD 적용 Scale 조회 | `sldControl/selectSLDScale.html` |
| 범례용 Element 생성(SLD) | SLD로 범례용 Elemnt 생성 | `sldControl/produceSLDElement.html` |
| wms 화살표 스타일 | 방향을 스타일로 표현 | `sldControl/wmsArrowStyle.html` |

## 10. Flat 스타일 / 스타일 표현식

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| Flat 단일 점 스타일 | Flat 단일 점 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simplePointStyle.html` |
| Flat 단일 타원 스타일 | Flat 단일 타원 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simplePointStyle_ellipse.html` |
| Flat 단일 심볼 스타일 | Flat 단일 심볼 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simpleSymbolStyle.html` |
| Flat 정다각형(regular shapes) 스타일 | Flat 정다각형(regular shapes) 스타일 생성하여 벡터레이어에 적용 | `flatStyle/simpleRegularShape.html` |
| Flat 단일 선 스타일 | Flat 단일 선 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simpleLineStyle.html` |
| Flat 단일 면 스타일 | Flat 단일 면 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simplePolygonStyle.html` |
| Flat 단일 라벨 스타일 | Flat 단일 라벨 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simpleLabelStyle.html` |
| Flat 복합스타일 | Flat 복합 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/complexStyle.html` |
| Flat 스타일 객체 ↔ JSON | 스타일 객체를 JSON 형태로 변경 | `flatStyle/simpleStyleCvt2JSON.html` |
| Flat 동적 스타일 | 동적 스타일을 생성하여 벡터 레이어에 적용 | `flatStyle/simpleFunctionStyle.html` |
| Flat 유형별 스타일(점-원형) | Flat 벡터레이어에 유형별 스타일 적용(점-원형) | `flatStyle/typeStyle.html` |
| Flat 유형별 스타일(점-심볼) | Flat 벡터레이어에 유형별 스타일 적용(점-심볼) | `flatStyle/typeSymbolStyle.html` |
| Flat 범위별 스타일 | Flat 벡터레이어에 범위별로 스타일 적용 | `flatStyle/rangeStyle.html` |
| Flat 범례용 Element | Flat 벡터레이어 범례용 Element 생성 | `flatStyle/createLegendElement.html` |
| webGL GeoTiff 레이어 스타일 | webGL GeoTiff 레이어 스타일 적용 | `flatStyle/webGLGeoTiffLayerStyle.html` |
| webGL Tile 레이어 스타일(kakao xyz) | webGL Tile 레이어 스타일 적용 | `flatStyle/kakaoXYZLayerStyle.html` |

## 11. 애니메이션

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 선을 따라 이동 애니메이션 | 선을 따라 아이콘이 이동하는 애니메이션 기능 적용 | `animation/followLineAnimation.html` |
| 파동 애니메이션 | 마우스 포인터 아래 도형이 있으면 파동 애니메이션 기능 적용 | `animation/waveAnimation.html` |
| 비행 애니메이션 | arc.js를 이용하여 출발지에서 도착지까지의 경로를 아크 형태로 애니메이션으로 표현 | `animation/flightAnimation.html` |
| 도형 점멸 애니메이션 | 깜빡이는 애니메이션 적용 | `animation/blinkAnimation.html` |

## 12. 오버레이

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 기본 마커 생성 | 마커를 생성 기능 제공 | `markerControl/marker.html` |
| 커스텀 마커 생성 | 커스텀 마커를 생성 기능 제공 | `markerControl/customMarker.html` |
| 마커로 이미지 레이어 유사하게 제작 | 마커를 이용하여 이미지를 지도 위에 올려 레이어와 비슷하게 이용 | `markerControl/imageLayerMarker.html` |
| 마우스 툴팁 생성 | 마커를 응용하여 마우스 커서를 따라다니는 툴팁 생성 | `markerControl/mouseTooltip.html` |
| 팝업 생성 | 팝업을 생성 기능 제공 | `markerControl/popup.html` |

## 13. 이벤트

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 이벤트 추가/해제 | 이벤트를 추가/해제 | `eventControl/basicEvent.html` |
| 지도 이벤트 | 지도 객체에 이벤트를 연결 | `eventControl/mapEvent.html` |
| 마커 이벤트 | 마커 객체에 이벤트를 연결 | `eventControl/markerEvent.html` |
| 뷰 이벤트 | 뷰 객체에 이벤트를 연결 | `eventControl/viewEvent.html` |
| 레이어 이벤트 | 레이어 객체에 이벤트를 연결 | `eventControl/layerEvent.html` |
| 이벤트 강제 실행 | 등록된 이벤트를 강제 실행 | `eventControl/triggerEvent.html` |
| 이벤트 등록 확인 | 이벤트가 등록되어있는지 확인 | `eventControl/hasEvent.html` |

## 14. 분석 레이어

| 예제명 | 설명 | 파일 경로 |
|--------|------|----------|
| 클러스터 레이어 | 클러스터 분석 레이어 표출 방법 | `analysisControl/cluster.html` |
| 클러스터 레이어 집계 데이터 위치 변경 | 집계 대상 정보를 이용해 집계 포인트 위치 변경.  | `analysisControl/cluster_positionChange.html` |
| 클러스터 레이어 응용 | 클러스터 레이어를 이용하여 인근에 있는 도형을 묶어 표출합니다. | `analysisControl/cluster_smaple.html` |
| geojson 타입으로 클러스터 레이어 생성 | CSV 형식의 데이터로 도형을 생성하는 기능 제공 | `analysisControl/cluster_geojson.html` |
| 애니메이션클러스터 레이어 | 애니메이션클러스터 분석 레이어 표출 방법 | `analysisControl/animateCluster.html` |
| 핫스팟 분석 레이어 | 핫스팟 분석 레이어 표출 방법 | `analysisControl/hotspot.html` |
| 밀집도 분석 레이어 | 밀집도 분석 레이어 표출 방법 | `analysisControl/heatmap.html` |
| 포인트집계 분석 레이어 | 포인트집계 분석 레이어 표출 방법 | `analysisControl/aggregate.html` |

---

## 통계

- **카테고리 수**: 14개
- **총 예제 수**: 159개

---

*이 파일은 `node scripts/build-samples.js` 명령으로 자동 생성되었습니다.*
