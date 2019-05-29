---
layout : post
title : Daily-Report 웨일 사이드바앱 개발 (2)
---
첫번째 Iteration의 목표인 <'한 일'과 '피드백'을 어떤 형태로든 사이드바에서 표시할 수 있어야 한다.>를 구현합니다.

이를 구현하기 위한 필수 요소는 다음과 같습니다.
- 웨일 사이드바에서 실행시킬 수 있도록 하는 매니페스트 파일
	- 확장프로그램이라면 필수적으로 가지고 있어야 합니다.
- html 파일
	- 한 일과 피드백을 표시합니다.
	- 목록을 나타내주기만 하면 되기 떄문에 간단하게 ul, li 태그만 사용해보겠습니다.
		- 어떤 지식을 습득하기 위해 어려운 것을 가져다 쓰지 않고, 목표를 달성할 수 있는 가장 간단한 방법을 사용하겠습니다.

#### manifest.json

    {
      "manifest_version" : 2, // 반드시 2로 적는다.
      "name": "Daily Report on Whale",
      "version": "1.0.0",
      "description": "Daily Report & Feedback on Whale SideBar",
      "icons": {
        "16" : "images/list_16.png",
        "64": "images/list_64.png"
      },
      
      "sidebar_action": {
        "default_page": "sidebar.html",
        "default_icon": {
          "16": "images/list_16.png"
    },
      "default_title": "데일리 리포트"
      }
    }

[Whale 개발자 센터 - 매니페스트](https://developers.whale.naver.com/api/manifest/)를 참고하여 필요한 매니페스트 키만을 사용하였습니다.
- 사이드바앱이기 때문에 sidebar_action은 반드시 지정해주어야 합니다.
- defualt_page는 사이드바의 아이콘을 클릭하면 열리는 HTML 페이지입니다.
- icon 이미지들은 flaticon에서 공책모양으로 가져왔습니다.
	- 16px 사이즈는 "16"의 value로 넣고, 64px 사이즈는 "64"에 넣습니다.

#### sidebar.html

    <!DOCTYPE html>
    <html lang="kr" dir="ltr">
      <head>
        <meta charset="utf-8">
        <title></title>
      </head>
      <body>
        <ul>
          <li>2019-05-29</li>
          <ol>
            <li>밥먹음</li>
            <li>설거지했음</li>
            <li>샤워했음</li>
          </ol>
          <li>피드백</li>
            <ul>
              <li>잡곡밥이 맛있었다.</li>
            </ul>
      </ul>
      </body>
    </html>

#### 테스트
whale://extensions/ 에 접속해 개발자모드를 ON하고 '압축해제된 확장프로그램을 로드합니다'를 클릭하여 작업하고 있던 디렉토리를 클릭합니다.
사이드바 아이콘을 클릭하여 실행시킵니다.
![Result Screenshot](/images/Iteration_1_result.jpg)
Iteration#1을 종료합니다.

