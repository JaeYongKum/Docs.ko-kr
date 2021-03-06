## <a name="overview"></a>개요

만들 API는 다음과 같습니다.

|API | 설명    | 요청 본문    | 응답 본문   |
|--- | ---- | ---- | ---- |
|GET /api/todo  | 할 일 항목 모두 가져오기 | 없음 | 할 일 항목의 배열|
|GET /api/todo/{id}  | ID로 항목 가져오기 | 없음 | 할 일 항목|
|POST /api/todo | 새 항목 추가 | 할 일 항목  | 할 일 항목 |
|PUT /api/todo/{id} | 기존 항목 업데이트 &nbsp;  | 할 일 항목 |  없음 |
|DELETE /api/todo/{id}  &nbsp;  &nbsp; | 항목 삭제 &nbsp;  &nbsp;  | 없음  | 없음|

<br>

다음 다이어그램에서는 앱의 기본 디자인을 보여 줍니다.

![클라이언트는 왼쪽에 상자로 표시되며 요청을 제출하고 오른쪽에 그린 상자인 응용 프로그램에서 응답을 받습니다. 응용 프로그램 상자 내에서 3개의 상자는 컨트롤러, 모델 및 데이터 액세스 계층을 나타냅니다. 요청은 응용 프로그램의 컨트롤러로 들어오고 읽기/쓰기 작업은 컨트롤러와 데이터 액세스 계층 간에 발생합니다. 모델은 직렬화되며 응답에서 클라이언트에 반환됩니다.](../../tutorials/first-web-api/_static/architecture.png)

* 클라이언트는 웹 API를 사용하는 어떤 것입니다(모바일 앱, 브라우저 등). 이 자습서에서는 클라이언트를 작성하지 않습니다. [Postman](https://www.getpostman.com/) 또는 [curl](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/curl.1.html)을 사용하여 앱을 테스트합니다.

* *모델*은 응용 프로그램에서 데이터를 나타내는 개체입니다. 이 경우 유일한 모델은 할 일 항목입니다. 모델은 C# 클래스로 표현되며 POCO(**P**lain **O**ld **C**# **O**bject)로도 알려져 있습니다.

* *컨트롤러*는 HTTP 요청을 처리하고 HTTP 응답을 만드는 개체입니다. 이 앱은 단일 컨트롤러를 갖습니다.

* 자습서를 간단히 유지하기 위해 앱은 영구 데이터베이스를 사용하지 않습니다. 샘플 앱은 메모리 내 데이터베이스에 할 일 항목을 저장합니다.
