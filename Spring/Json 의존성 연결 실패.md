## Json 의존성 연결 실패 문제

> @ResponseBody 또는 @RestController를 이용하여 사용자 요청의 결과를 Json으로 반환하기 위해 jackson을 추가시킬 때 발생하는 문제입니다.
>
> 검색해보면, maven 빌드가 재대로 안되었다던지 jackson-databind dependency가 추가되지 않았다고 나옵니다.
>
> 그 정도의 문제라면 쉽게 해결할 수 있지만 위의 경우가 아닌 JDK 버전의 차이로 발생하는 문제도 있습니다.
>
> JDK1.6을 사용 시 jackson 버전이 너무 최신이라던지 버전에 맞지 않아 발생하는 문제점도 있습니다.



#### **오류메시지**

```
SpringMVC5 org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter': Instantiation of bean failed; nested exception is org.springframework.beans.BeanInstantiationException: Failed to instantiate [org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter]: Constructor threw exception; nested exception is java.lang.NoClassDefFoundError: com/fasterxml/jackson/databind/exc/InvalidDefinitionException
```

   

### 해결법

> 필자는 JDK 11 기준으로 작성하였습니다. jackson 2.9.7 버전에도 동일한 문제점을 확인하여 2020년11월 업데이트 버전인 2.12.0 최신 버전을 
>
> 설정하여 해결했습니다.

**pom.xml 수정**

```xml
		<dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-core</artifactId>
            <version>2.12.0</version>
        </dependency>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.12.0</version>
        </dependency>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-annotations</artifactId>
            <version>2.12.0</version>
        </dependency>
```
