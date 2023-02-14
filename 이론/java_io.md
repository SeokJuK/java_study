# IO
- Input & Output
- 입출력
- 입력은 키보드, 네트워크, 파일등으로부터 받을 수 있다
- 출력은 화면, 네트워크, 파일등에 할 수 있다

# Java IO는 조립되어 사용되도록 만들어졌다
- Decorator 패턴으로 만들어졌다(장식)

# 주인공과 장식을 구분
- 장식은 InputStream, OutputStream, Reader, Writer->(Component역할)를 생성자에서 받아들인다
- 주인공은 어떤 대상에게서 읽어들일지, 쓸지를 결정한다
- 주인공은 1byte or byte[] 단위로 읽고 쓰는 메소드를 가진다
- 주인공은 1char or char[] 단위로 읽고 쓰는 메소드를 가진다
- 장식은 다양한 방식으로 읽고 쓰는 메소드를 가진다

# Java IO의 특수한 객체
- System.in: 표준 입력(InputStream) -> 키보드로부터 입력
- System.out: 표준 출력(PrintStream) -> 화면 출력
- System.err: 표준 에러 출력(PrintStream) -> 화면 출력

# 키보드로부터 한줄씩 입력받고 한줄씩 화면에 출력하기
```java
/*
키보드 -> System.in(InputStream 주인공)
화면에 출력: System.out(PrintStream 주인공)
키보드로 입력받는다는건 문자를 입력받는 것: char단위 입출력
char단위 입출력 클래스 : Reader, Writer
한줄 읽기 : BufferedReader라는 클래스 -> readLine이라는 메소드
더이상 읽어드릴 것이 없으면(EDF) Null을 반환
한줄 쓰기: PrintStrea, PrintWriter
BufferedReader는 장식이다 -> 주인공이 있어야 사용 가능하다
*/
// BufferedReader x -> BufferedReader인스턴스를 만드려는데 또 사용 x
// CharReader x -> 문자를 읽어들이니까

BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String line = null;
while((line = br.readLine()) !=null{//한줄 입력받는다
  System.out.prinln(line); //읽어들인값
}
```

# File 클래스
- java.io.File 클래스는 파일의 크기, 파일의 접근 권한, 파일의 삭제, 이름의 변경 등의 작업을 할 수 있는 기능을 제공
-- 디렉토리(폴더) 역시 파일로서 취급된다는 점을 주의

