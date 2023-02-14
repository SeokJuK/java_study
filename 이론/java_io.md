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
