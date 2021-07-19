---
layout: post
title: SwiftUI 네이버 지도에 터치이벤트 적용하기
subheading: SwiftUI Naver Map Touch Event apply
author: JunHo
categories: SwiftUI
banner: https://bit.ly/32PAjtM
tags: SwiftUI app design apple android keyboard devloper naver kakao map API Touch Event apply
sitemap :
  changefreq : daily
  priority : 1.0




---





## 네이버 지도에 터치이벤트 적용하기

---

이전 포스트 글에 이어서 이번에는 지도에 터치이벤트를 적용시켜 보도록 하겠다.



```swift
// MapView.swift
import SwiftUI
import KeyboardToolbar
import MapKit
import NMapsMap
import Combine

struct MapView: UIViewRepresentable {
    @ObservedObject var viewModel = MapSceneViewModel()
    @State var userLatitude: Double
    @State var userLongitude: Double
    
    func makeUIView(context: Context) -> NMFNaverMapView {
        let view = NMFNaverMapView()
        view.showZoomControls = false
        view.mapView.zoomLevel = 17
        view.mapView.mapType = .hybrid
        view.mapView.touchDelegate = context.coordinator
        
        let cameraUpdate = NMFCameraUpdate(scrollTo: NMGLatLng(lat: userLatitude, lng: userLongitude))
        view.mapView.moveCamera(cameraUpdate)
        return view
    }
    
    func updateUIView(_ uiView: NMFNaverMapView, context: Context) {}
    
    
    class Coordinator: NSObject, NMFMapViewTouchDelegate, NMFMapViewCameraDelegate, NMFMapViewOptionDelegate {
        @ObservedObject var viewModel: MapSceneViewModel
        var cancellable = Set<AnyCancellable>()
        
        init(viewModel: MapSceneViewModel) {
            self.viewModel = viewModel
        }
        func mapView(_ mapView: NMFMapView, didTapMap latlng: NMGLatLng, point: CGPoint) {
            print("지도 탭")
        }
    }
    
    func makeCoordinator() -> Coordinator {
        return Coordinator(viewModel: self.viewModel)
    }
}

class MapSceneViewModel: ObservableObject {
    
}

```

코드는 위와 같다. 이전 포스트글에서 달라진 점은 **makeUIView** 함수에 **view.mapView.touchDelegate = context.coordinator**가 추가되었고 makeCoordinator 함수와 내부 클래스로 Coordinator이 추가되었다. SwiftUI 방식에서는 따로 Delegate가 존재하지 않는다. 왜냐하면 ViewController가 존재하지 않기때문이다. 따라서 애플이 Delegate를 살리기 위해 만들어 둔 Coordinator를 사용하였다. 그리고 네이버 지도의 touchDelegate에 적용시키면 자동으로 mapView라 호출되어서 지도 탭(터치)시 print문이 출력되게 된다.

위 터치 이벤트를 구현하기 위해 참고한 곳은 [Sweet_Dev님 블로그](https://sweetdev.tistory.com/447)를 참고하여 구현하였다.



## 결과

![스크린샷 2021-07-19 오후 1.53.25](/assets/images/스크린샷 2021-07-19 오후 1.53.25.png)

위 사진과 같이 지도를 탭하면 print문이 출력되게 된다.

