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

# Java IO 클래스 이름
- Stream으로 끝나는 클래스 -> byte단위 입출력 클래스
- InputStream으로 끝나느 클래스 -> byte단위로 입력을 받는 클래스
- OutputStream으로 끝나는 클래스 -> byte단위로 출력을 하는 클래스
- Reader로 끝나는 클래스 -> 문자 단위로 입력을 받는 클래스
- Writer로 끝나는 클래스 -> 문자 단위로 출력을 하는 클래스
- File로 시작할 경우(File 클래스 제외) -> File로부터 입력이나 출력을 하는 클래스
- ByteArray로 시작할 경우 -> 입력 클래스 경우 byte 배열로부터 읽어 들이고, 출력클래스의 경우 내부 자료구조에 출력을 한 후 출력된 결과를 byte배열로 반환
- CharArray로 시작할 경우 -> char
- Filter로 시작할 경운 -> 사용하는 것 보단 상속을 받아 사용하고, 사용자가 원하는 내용만 필터링
- Data로 시작할 경우 -> 다양한 데이터 형을 입출력, 특히 기본형(int float double)등 출력하는데 유리
- Buffered로 시작하는 경우 -> 입출력시 병목현상을 줄일 때
- RandomAccessFile -> 입출력을 모두 할 수 있는 클래스, 파일에서 임의의 위치에서 내용을 읽거나 쓸 수 있다

# 주인공과 장식을 구분하는 방법
- 생성자에 InputStream, OutputStream, Reader, Writer이 있으면 장식

