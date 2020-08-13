# HTML(Hyper Text Markup Language)
- **웹페이지를 위한 표준 마크업 언어.**
- 마크업 언어란? 태그(tag) 등을 이용하여 문서나 데이터의 구조를 명기하는 언어.
- 태그(tag)란? 의류의 택(tag)을 생각하면 됨. 그 택에는 의류에 관한 가격 등 기타 정보들이 들어있음. html에서 태그도 그 고유의 정보를 갖고 있음.
- hyper text란? text를 초월(hyper)하다. 우리가 text를 읽을 땐 왼쪽 상단에서 우측 하단으로 순차적으로 정보에 접근한다. hyper가 붙어서 순차적으로 정보에 접근하는 것을 뛰어넘는다는 의미(=링크를 이용해 원하는 곳으로 바로 이동 가능).
- markup이란? 텍스트를 표시하는 방법을 나타내는 데 사용되는 기법. 쉽게 말해 화면에 표시해주는 것임.

# CSS(Cascading Style Sheets)
- **HTML이나 XML로 작성된 문서들의 스타일을 기술하는 스타일시트 언어.**
- 왜 cascading인가? cascading(폭포같은, 연속적인), 상위 요소의 스타일 속성을 자손 요소들에게 상속시켜주는 모습이 DOM 트리구조에서 마치 폭포수처럼 내려가는 모습을 닮았기 때문.

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
- 다양한 기능들이 이미 내장되어 있음. http client, router, 다국어 지원 등 모두 내장되어 있음
- typescript가 기본임.
## React(라이브러리)
- 사용자는 view만 신경쓰고 나머지는 써드파티 라이브러리 활용.
- 생태계가 굉장히 넓음.
## Vue(프레임워크)
- 입문자가 사용하기 쉬움.
- 공식 라우터와 공식 상태관리 라이브러리가 존재함.

