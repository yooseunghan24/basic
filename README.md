# HTML(Hyper Text Markup Language)
- **웹페이지를 위한 표준 마크업 언어.**
- 마크업 언어란? 태그(tag) 등을 이용하여 문서나 데이터의 구조를 명기하는 언어.
- 태그(tag)란? 의류의 택(tag)을 생각하면 됨. 그 택에는 의류에 관한 가격 등 기타 정보들이 들어있음. html에서 태그도 그 고유의 정보를 갖고 있음.
- hyper text란? text를 초월(hyper)하다. 우리가 text를 읽을 땐 왼쪽 상단에서 우측 하단으로 순차적으로 정보에 접근한다. hyper가 붙어서 순차적으로 정보에 접근하는 것을 뛰어넘는다는 의미(=링크를 이용해 원하는 곳으로 바로 이동 가능).
- markup이란? 텍스트를 표시하는 방법을 나타내는 데 사용되는 기법. 쉽게 말해 화면에 표시해주는 것임.

# CSS(Cascading Style Sheets)
- **HTML이나 XML로 작성된 문서들의 스타일을 기술하는 스타일시트 언어.**
- 왜 cascading인가? cascading(폭포같은, 연속적인), 상위 요소의 스타일 속성을 자손 요소들에게 상속시켜주는 모습이 DOM 트리구조에서 마치 폭포수처럼 내려가는 모습을 닮았기 때문. 코드상에서 아래 있는 스타일이 적용됨.

# HTTP(Hyper Text Transfer Protocol)
- HTTP는 클라이언트와 서버 사이에 이루어지는 요청/응답 **프로토콜**이다. HTML 문서와 같은 리소스들을 가져올 수 있도록 해줌. 웹에서 이루어지는 모든 데이터 교환의 기초.
- **프로토콜**이란? 컴퓨터끼리 또는 컴퓨터와 단말기 사이 등에서 정보교환이 필요한 경우, 이를 원활하게 하기 위하여 정한 여러 가지 통신규칙과 방법에 대한 약속이다. 이 약속에는 상호간의 접속이나 전달방식, 통신방식, 주고받을 자료의 형식, 오류검출방식, 코드변환방식, 전송속도 등에 대하여 정함. TCP/IP 레이어를 기반으로 사용 함.
- 인터넷 주소를 지정할 때 'http://www...'와 같이 하는 것은 www로 시작되는 인터넷 주소에서 하이퍼텍스트 문서의 교환을 http 통신규약으로 처리하라는 뜻임.
- HTTP는 웹 처리 전반에 걸쳐 토대가 되기 때문에 웹 서버를 HTTP 서버라고 부르기도 함.
- 클라이언트-서버 프로토콜이란 수신자 측에 의해 요청이 초기화되는 프로토콜을 의미함.
- HTML과 같은 하이퍼미디어 문서를 전송하기위한 응용 계층(Application layer) 프로토콜.
- 서버와 클라이언트 사이에서 어떻게 메시지를 교환할 것인지 정해놓은 규칙.
- 1990년대 초 설계됨.
- 신뢰 가능한 전송 프로토콜이라면 이론상으로는 무엇이든 사용할 수 있으나 TCP 혹은 암호화된 TCP 연결인 TLS를 통해 전송됨.
- HTTP의 확장성 덕분에 오늘날 하이퍼텍스트 문서 뿐만 아니라 이미지와 비디오 혹은 HTML폼 결과와 같은 내용을 서버로 POST하기 위해서도 사용됨.

## 대표적인 status
### 200 OK
- 파일 변경시간이 서로 다르거나 파일크기 등이 서로 맞지 않으면 이때는 200 응답을 내고 서버는 요청한 파일을 클라이언트에게 전달합니다.
- 클라이언트는 200 응답코드를 받았으므로 기존의 파일이 있다면 삭제하고 새로운 파일로 대체 또는 캐시하게 됩니다.
- 대부분 동적인 파일(PHP)은 항상 200 응답을 냅니다. 반면 정적인 HTML 이나 gif, jpg, png, mp3, mpg, asf 등은 거의 대부분 304로 응답합니다.
### 304 Not Modified
- 자신의 HDD 공간에 있는(cached) 파일의 정보, 그러니깐 마지막으로 변경된 시간이나 파일크기 등등의 정보를 포함해서 서버에게 요청합니다.(요청헤더에 붙음)
- 서버는 클라이언트가 보낸 요청헤더 정보를 보고, 자신의 웹서버에 있는 파일 정보와 비교합니다. 이때 파일 변경시간과 크기등이 서로 같으면 서버는 304 로 응답합니다.
- 즉 이것은 클라이언트에 있는 파일과 서버에 있는 파일이 서로 같으므로 클라이언트 HDD 에 있는 파일을 사용하라 라는 의미이고 실제로 파일 전송은 이루어지질 않습니다.

## 역사
### HTTP/0.9
### HTTP/1.0
### HTTP/1.1
### HTTP/2.0
- 지연 시간을 감소시켜 웹의 속도를 개선하기 위해 등장.
- 전체 요청과 응답 멀티플렉싱을 가능하게 하여 HTTP 헤더 필드를 효율적으로 압축함으로써 프로토콜 오버헤드 최소화.
- Server Push
- 멀티플렉싱
  + 프레임마다 관련된 요청 순서 번호(stream #)를 기재.
  + 요청 순서에 상관없이 데이터 전송 가능.
  + 하나의 TCP 세션 사용.
- 헤더 압축
  + 이전 헤더 내용을 테이블에 저장.
  + 다음 request에서 동일한 헤더를 사용할 경우 테이블의 Index 번호만 사용.
- Server Push
  + client가 요청하기 전에 필요가 예상되는 리소스를 server가 먼저 전송함.
#### HTTP/1.x 메시지는 성능상의 결함을 몇가지 내포하고 있음.
- 본문은 압축이 되지만 헤더는 압축이 되지 않음.
- 연속된 메시지들은 비슷한 헤더 구조를 띄기 마련인데, 그럼에도 불구하고 메시지마다 반복되어 전송되고 있음.
- 다중전송(multiplexing)이 불가능함. 서버 하나에 연결을 여러개 열어야 함.
#### HTTP/2에서 추가적인 단계가 도입됨.
- HTTP/1.x 메시지를 프레임으로 나누어 스트림에 끼워 넣음.
- 데이터와 헤더 프레임이 분리 되었기 때문에 헤더를 압축할 수 있음.
### HTTP/3
- TCP대신 QUIC라는 새로운 UDP 프로토콜을 사용함.

# GET/POST
# GET
- GET은 서버로부터 정보를 조회하기 위해 설계됨.
### 언제 사용하나?
#### get은 서버에서 어떤 데이터를 가져와서 보여줄때 사용함. 어떤 값이나 내용, 상태 등을 바꾸지 않는 경우에 사용. 예를들면 게시판에서 글의 내용에 대한 목록을 보여주는 경우나, 글의 내용을 보는 경우에 사용.
### 특징
- GET은 요청을 전송할 때 필요한 데이터를 Body에 담지 않고, **쿼리스트링**을 통해 전송함.(쿼리스트링: URL의 끝에 ?와 함께 이름과 값으로 쌍을 이루는 요청 파라미터. 만약, 요청 파라미터가 여러개면 &로 연결함.)
- 한번의 데이터 요청시,전송 데이터의 양은 주소값+파라미터로  255자로 제한이 됨.
- 쿼리스트링을 사용하게 되면 URL에 조회 조건을 표시하기 때문에 특정 페이지를 링크하거나 북마크할 수 있음.
- 예: www.example-url.com/resources?name1=value1&name2=value2 여기서 요청 파라미터명은 name1, name2이고, 각각의 파라미터는 value1, value2라는 값으로 서버에 요청을 보내게 됨.
- GET은 불필요한 요청을 제한하기 위해 요청이 캐시될 수 있음.
- js, css, 이미지 같은 정적 컨텐츠는 데이터양이 크고, 변경될 일이 적어서 반복해서 동일한 요청을 보낼 필요가 없음.
- 정적 컨텐츠를 요청하고 나면 브라우저에서는 요청을 캐시해두고, 동일한 요청이 발생할 때 서버로 요청을 보내지 않고 캐시된 데이터를 사용함.
- 그래서 프론트엔드 개발을 하다보면 정적 컨텐츠가 캐시돼 컨텐츠를 변경해도 내용이 바뀌지 않는 경우가 종종 발생함.
- 이 때는 브라우저의 캐시를 지워주면 다시 컨텐츠를 조회하기 위해 서버로 요청을 보내게 됨.
# POST
- POST는 리소스를 생성/변경하기 위해 설계됨.
### 언제 사용하나?
#### post는 서버상의 데이터 값이나 상태를 바꾸기 위해서 사용함. 글쓰기를 예를들면 글의 내용을 저장하고, 수정할때에 post를 사용하는 것임.
### 특징
- GET과 달리 전송해야될 데이터를 HTTP 메세지의 Body에 담아서 전송함.
- HTTP 메세지의 Body는 길이의 제한없이 데이터를 전송할 수 있음(GET과 달리 대용량 데이터 전송 가능).
- 이처럼 POST는 데이터가 Body로 전송되고 내용이 눈에 보이지 않아 GET보다 보안적인 면에서 안전하다고 생각할 수 있지만, POST 요청도 크롬 개발자 도구, Fiddler와 같은 툴로 요청 내용을 확인할 수 있기 때문에 민감한 데이터의 경우에는 반드시 암호화해 전송해야 함.
- 그리고 POST로 요청을 보낼 때는 요청 헤더의 Content-Type에 요청 데이터의 타입을 표시해야 함.
- 데이터 타입을 표시하지 않으면 서버는 내용이나 URL에 포함된 리소스의 확장자명 등으로 데이터 타입을 유추함.
- 만약, 알 수 없는 경우에는 application/octet-stream로 요청을 처리함.
## HTTP 패킷이란?
- 웹에서 get과 post 방식으로 서버로 요청을 했을때, 보내는 데이터를 HTTP 패킷이라 표현한다.
- HTTP 프로토콜을 쓰므로, 앞에 HTTP가 붙고 인터넷을 통해 보내는 데이터를 패킷이라 표현하므로 HTTP패킷 이라 부른다.
- HTTP 패킷의 구조는 크게 헤더 와 바디로 나뉘어진다.
- get 방식에서는 앞에서 말한 패킷의 헤더에 www.example.com?id=mommoo&pass=1234 과 같은 형식으로 url을 통해 데이터를 보냈었다면, post 방식은 패킷의 body라고 불리는 것 안에(웹 사용자는 볼수 없습니다.) 데이터를 담아서 보내게 됩니다.
- 따라서, url상에 보이지 않아도 데이터를 전송할 수 있었던 것이었습니다.
## GET과 POST의 차이
- GET은 Idempotent, POST는 Non-idempotent하게 설계됨.
- Idempotent(멱등)은 수학적 개념으로 다음과 같이 나타낼 수 있음.
  + 멱등이란? 수학이나 전산학에서 연산의 한 성질을 나타내는 것으로, 연산을 여러 번 적용하더라도 결과가 달라지지 않는 성질.
- 즉, 멱등이라는 것은 동일한 연산을 여러 번 수행하더라도 동일한 결과가 나타나야 함.
- 여기서 GET이 Idempotent하도록 설계되었다는 것은 GET으로 서버에게 동일한 요청을 여러 번 전송하더라도 동일한 응답이 돌아와야 한다는 것을 의미함.
- 이에 따라 GET은 설계원칙에 따라 서버의 데이터나 상태를 변경시키지 않아야 Idempotent하기 때문에 주로 조회를 할 때에 사용해야함.
- 예를 들어, 브라우저에서 웹페이지를 열어보거나 게시글을 읽는 등 조회를 하는 행위는 GET으로 요청하게 됨.
- 반대로 POST는 Non-idempotent하기 때문에 서버에게 동일한 요청을 여러 번 전송해도 응답은 항상 다를 수 있음.
- 이에 따라 POST는 서버의 상태나 데이터를 변경시킬 때 사용됨.
- 게시글을 쓰면 서버에 게시글이 저장이 되고, 게시글을 삭제하면 해당 데이터가 없어지는 등 POST로 요청을 하게 되면 서버의 무언가는 변경되도록 사용됨.
- 이처럼 POST는 생성, 수정, 삭제에 사용할 수 있지만, 생성에는 POST, 수정은 PUT 또는 PATCH, 삭제는 DELETE가 더 용도에 맞는 메소드라고 할 수 있음.

- 마지막으로 웹페이지를 조회할 때, 링크를 통해 특정 페이지로 바로 이동하려면 해당 링크와 관련된 정보가 필요한데 POST는 요청 데이터가 Body에 담겨 있기 때문에 링크 정보를 가져올 수 없음.
- 반면, GET은 URL에 요청 파라미터를 가지고 있기 때문에 링크를 걸 때, URL에 파라미터를 사용해 더 디테일하게 페이지를 링크할 수 있음.
# TCP(Transmission Control Protocol)

# IP(Internet Protocol)

# UDP

# HTTPS(HyperText Transfer Protocol over Secure Socket Layer)

# API(Application Programming Interface)
- API는 이미 만들어진 코드의 집합체라고 볼 수 있으며, 개발자들이 만들기 어렵고 힘든 부분을 쉽게 구현하도록 하는 프로그램이라고 볼 수 있음. 마치 집에서 가구를 만들 때 직접 디자인하고, 재료를 구하고, 재단하고, 못을 박고 하는 등 혼자서 모든 것을 하는 대신 가구 만들기 키트를 사는 것과 같다고 보면 됨.

# Ajax(Asynchronous JavaScript and XML)
- 자바스크립트를 이용해서 비동기적(Asynchronous)으로 서버와 브라우저가 데이터를 교환할 수 있는 통신 방식을 의미함.
- 서버로부터 웹페이지가 반환되면 화면 전체를 갱신해야 하는데 페이지 일부만을 갱신하고도 동일한 효과를 볼 수 있도록 하는 것이 Ajax이다. 페이지 전체를 로드하여 렌더링할 필요가 없고 갱신이 필요한 일부만 로드하여 갱신하면 되므로 빠른 퍼포먼스와 부드러운 화면 표시 효과를 기대할 수 있다.

# JSON(Javascript Object Notation)
- 클라이언트와 서버 간에는 데이터 교환이 필요하다. JSON(JavaScript Object Notation)은 클라이언트와 서버 간 데이터 교환을 위한 규칙 즉 데이터 포맷을 말한다.
- JSON은 일반 텍스트 포맷보다 효과적인 데이터 구조화가 가능하며 XML 포맷보다 가볍고 사용하기 간편하며 가독성도 좋다.
- 자바스크립트의 객체 리터럴과 매우 흡사하다. 하지만 JSON은 순수한 텍스트로 구성된 규칙이 있는 데이터 구조이다.

# 자바스크립트 프레임워크, 라이브러리 비교
## Angular(프레임워크)
- 다양한 기능들이 이미 내장되어 있음. http client, router, 다국어 지원 등 모두 내장되어 있음.
- typescript가 기본임.
## React(라이브러리)
- 사용자는 view만 신경쓰고 나머지는 써드파티 라이브러리 활용.
- 생태계가 굉장히 넓음.
## Vue(프레임워크)
- 입문자가 사용하기 쉬움.
- 공식 라우터와 공식 상태관리 라이브러리가 존재함.

# 데이터베이스
## 관계형 데이터베이스(Relational DBMS)
- 데이터를 표의 형태로 저장하여 검색, 정렬 등을 빠르고 안전하게 할 수 있음.
## NoSQL DBMS(Not only SQL DBMS)
- SQL만을 사용하지 않는 데이터베이스 관리 시스템(DBMS)을 지칭하는 단어이다. 관계형 데이터베이스를 사용하지 않는다는 의미가 아닌, 여러 유형의 데이터베이스를 사용하는 것이다.
- MongoDB: 크로스 플랫폼 도큐먼트 지향 데이터베이스 시스템.

# 기타 팁
- 어떤 태그가 동적으로 생성되었어도 html 문서에 뿌려준 다음에는 이벤트나 css를 먹일 수 있음. ㅎㅎ

# PHP & MYSQL


# 웹접근성
- 웹 접근성(web accessibility)은 장애인이나 고령자분들이 웹 사이트에서 제공하는 정보를 비장애인과 동등하게 접근하고 이용 할 수 있도록 보장하는 것으로 웹 접근성 준수는 법적의무사항.
# 웹표준
# 크로스브라우징
