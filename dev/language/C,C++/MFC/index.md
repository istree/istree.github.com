---
layout: dev
title: MFC
---

## 코드

### 출력 창에 메시지 출력(MFC)

```C++
OutputDebugString(_T("Hello world.\n"));
```

```C++
#ifdef _DEBUG
TRACE("character Name : \n");
#endif //_DEBUG
```

### 마우스 커서로 색상 추출(MFC)

현재 창을 벗어나도 마우스 이벤트를 받을수 있는 아래 API를 사용한다.

```C++
SetCapture(); 
ReleaseCapture();
```

다만 위 API는 WM_LBUTTONDOWN 이 유지될 동안만 유효하다.

#### 참고문서
[ColorFinder](https://www.codeproject.com/Articles/5009/ColorFinder-Retrieve-the-color-of-any-pixel-on-the)

### Editing CWnd를 Popup으로 띄우기(MFC)

```c++
CWndFrame* m_pWndFrame = new CWndFrame();
CString strClass = AfxRegisterWndClass(CS_HREDRAW|CS_VREDRAW, 0, 
(HBRUSH (COLOR_WINDOW + 1));
m_pWndFrame->CreateEx( WS_EX_TOOLWINDOW|WS_EX_TOPMOST, 
strClass, _T("1234"), WS_POPUP, 5, 5, 500, 100, m_hWnd, NULL, NULL );
m_pWndFrame->ShowWindow( SW_SHOW );
```

1. Create() 함수를 사용하면 안된다.
2. 두번째 인자를 AfxRegisterWndClass(..)를 사용해서 넣는다.