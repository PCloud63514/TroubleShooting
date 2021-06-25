## Error MS949

> 이 에러는 IntelliJ 에서 확인하였습니다. eclipse에서는 정상 작동합니다.
>
> MS949 말고도, **Could not initialize class java.nio.file.FileSystems$DefaultFileSystemHolder** 이런 Error도 함께 확인할 수 있습니다.
>
> Error 메시지에서 MS949라 인코딩 문제인가 싶기도 하고 SystemHolder가 나와 경로 문제인가 싶었지만, 새로운 프로젝트를 만들고 아무 로직 코드도 없는 상태에서 실행을 시켜도 아래와 같은 에러를 확인합니다.

![NS49Error](https://user-images.githubusercontent.com/22608825/98330164-1efe2c80-203d-11eb-8160-1c88fb9fd628.PNG)



### 해결법

> jdk 문제일 가능성이 높습니다. 전 jdk8을 사용하였으며 삭제 후 jdk 11을 재설치 후 Project Structure의 SDK과 language level을 11로 변경한 뒤 해결됬습니다.