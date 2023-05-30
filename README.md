3# Electron

## Electron? 
Chromium과 Node.js를 기반으로, HTML+JS+CSS를 이용하여 데스크톱 프로그램 개발을 가능하게 해주는 프레임워크

- Electron을 활용한 프로그램들 : Slack, VSCode, Atom, Figma
- 장점: 하나의 코드로 Windows, Mac, Linux 모두를 지원할 수 있음
- 단점: Chromium, Node Module을 포함하므로 가벼운 기능을 제공하더라도 100MB 이상의 저장공간이 필요하고, 속도와 메모리 측면에서도 가볍지는 않음
- 

## 동작 원리
- 1개의 메인(Main) 프로세스와 N개의 렌더러(Renderer) 프로세서로 구성됨
- 메인(Main) 프로세스는 Node.js 기반으로 동작. Local File System에 접근하여 작업 처리
- 렌더러(Renderer) 프로세스는 Chromium 기반으로 화면(UI)을 구성
- 메인 프로세스는 1개인 반면, 렌더러 프로세는 독립적으로 작동하기 때문에 0개 이상일 수 있음
- 메인 프로세스가 종료되면 렌더러 프로세스도 종료됨
- 메인 프로세서가 렌더러 프로세스를 생성하고 관리함
- 이를 위해 메인 프로세스와 렌더러 프로세스 간에는 ipcMain과 ipcRenderer와 같은 IPC 모듈을 통해 프로세스 간의 통신이 이루어짐


## 화면 안에 여러 화면 그리기: BrowserView
- BrowserView는 렌더러 프로세스의 가장 큰 단위이며, 하나의 윈도우 창을 의미함. 즉, 화면을 여러개의 영역으로 나눈다는건 여러개의 BrowserView를 띄운다는 것.
- BrowserView를 그리기 위해서는 BrowserWindow 내에서의 특정 위치, 높이, 넓이를 지정해줘야 함. 
- BrowserView는 모두 독립적인 브라우저라고 봐야하기 때문에(BrowserView간 직접적 통신 불가), 모든 BrowserView가 하나의 이벤트에 대해 반응하기 위해서는 메인 프로세스를 이용해 뷰간의 상태 값을 공유해야 함.


## chatGPT가 추천해준 toy project 주제
- Markdown Editor: Create a simple text editor that supports Markdown syntax highlighting and live preview.
- Pomodoro Timer: Build a Pomodoro timer app that helps users manage their time using the Pomodoro technique.
- Weather App: Develop a weather application that fetches real-time weather data from an API and displays it in a user-friendly interface.
- Expense Tracker: Create a budgeting app that allows users to track their income and expenses, set budgets, and generate reports.
- Recipe Finder: Build an app that lets users search for recipes based on ingredients they have on hand. It can fetch recipes from an API and display them with step-by-step instructions.
- Password Manager: Develop a secure password manager app that allows users to store and retrieve their passwords in an encrypted format.
- Task Manager: Create a simple task management app where users can create, organize, and track their tasks and to-do lists.
- Music Player: Build a basic music player app that can play local audio files and display basic playback controls.
- Image Gallery: Develop an app that allows users to browse and organize their local image collection with features like tagging, filtering, and slideshow mode.
- Note-Taking App: Create a note-taking application that lets users create, edit, and organize text-based notes with features like search, tagging, and markdown support.