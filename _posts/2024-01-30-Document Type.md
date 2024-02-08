---
title: "Document Type"
date: 2024-01-30 +0900
categories: [Webmethods, 설치 및 개발가이드]
tags: [EAI, webmethods]
order: 4
---

>웹메소드에서 사용하는 도큐먼트에 대해 간략하게 알아보고 실습에 대한 포스팅을 진행 해보겠습니다.


## Integration Server Documents & Document types

---



### A Document Type

![Untitled](/assets/img/2024-01-30-documenttype/Untitled.png)

- **도큐먼트의 유형/정의입니다. 도큐먼트에 포함된 필드에 대한 메타 정보가 포함되어 있습니다.**
- **디자이너에서 사용하는 요소입니다**
- **런타임에 문서의 유효성을 검사하는 데 사용할 제약 조건을 정의할 수 있습니다.**
- **더 나은 재사용을 위해 다른 도큐먼트 타입을 참조할 수 있습니다.**
- **JSON 또는 XML 데이터가 Document native인 IData로 변환 된 것입니다.**
- **데이터로 채워지며 Integration Server의 파이프라인을 통해 흐릅니다.**
- **XML이나 JSON이 아니며 Java 유형의 내부 데이터 객체입니다. (com.wm.data.IData)**

## Why XML Document Types?

---

- XML 스키마 기반 문서는 XML 문서 유형으로 표시될 수도 있습니다.
- XML 문서 유형은 XML 스키마 정의를 보다 정확하게 표현하고 다음과 같은 표준 IS 도큐먼트타입을 통해 지원되지 않는 XML 스키마 구성 및 기능에 대한 지원을 제공합니다.
    - 향상된 XML 네임스페이스 처리
    - 중첩되거나 반복된 모델 그룹 지원
    - 모든 속성 지원
    - 대체 그룹 또는 모든 요소에 대한 지원 개선
    - 단순 유형(문자열 필드)에서 xsi:nil 및 xsi:type을 지원합니다. IS 도큐먼트타입은 복합 유형(도큐먼트 필드)에서만 xsi:nill 및 xsi:type을 지원합니다.

## Why JSON Document Types?

---

- JSON 도큐먼트타입은 JSON 스키마를 기반으로 하며 검증과 관련된 JSON 스키마 기능을 제공합니다. 각 JSON 도큐먼트타입의 인스턴스는 루트 문서를 포함합니다. 이 루트 문서 내에서 인스턴스는 다음을 포함할 수 있습니다:
- JSON 스키마 필드에 해당하고 검증 속성을 포함하는 필드.
- 다른 JSON 문서 유형으로서 주어진 JSON 스키마의 다른 JSON 객체에 해당하는 것들.

## 사용자 정의 도큐먼트 만들어보기

---

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%201.png)

디자이너에서 오른쪽마우스 버튼을 눌러 Document Type을 클릭 해줍니다.

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%202.png)

이름을 입력하고 Next를 눌러줍니다.

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%203.png)

None으로 선택하시고 Finish를 눌러줍니다

**다른 선택사항들은 위에서 설명드린 스키마등 참조 문서를 활용하여 도큐먼트를 만드는 방법
입니다. 하지만 일반적인 개발에서는 정의서에 따라 도큐먼트를 만드는 경우가 많다보니
사용자 정의로 대부분 만든다고 생각하시면 됩니다**

도큐먼트에 필드를 추가 해보겠습니다.
palette에서 string 필드 두개를 드래그해서 추가해주면 됩니다

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%204.png)

현재 구조를 JSON, XML로 표현하면 아래와 같습니다
**스키마로 표현해야 하는게 맞지만 이해를 돕기 위해 간략하게 표시했습니다.**

```json
{
  "person" : {
			"name" : "",
			"phone" : ""
	} 
}
```

```xml
<person>
	<name/>
	<phone/>
</person>
```

네 도큐먼트는 하나의 객체라고 보시면 됩니다
도큐먼트 안에 또 도큐먼트를 정의할 수 있고
도큐먼트리스트 등 여러가지 필드를 정의 할 수 있습니다
다음은 도큐먼트 안에 도큐먼트를 정의 해 보겠습니다.

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%205.png)

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%206.png)

city라는 string 필드를 정의하고 address의 하위 필드로 정의하기 위해서는
위 그림처럼 city 필드를 클릭한 뒤 Move Right 아이콘을 클릭해줍니다 

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%207.png)

**JSON , XML**

```json
{
    "person" : {
        "name" : "",
        "phone" : "",
        "Address" : {
            "city" : "",
            "steet" : ""   
        }
        
    }
}
```

```xml
<person>
	<name/>
	<phone/>
	<address>
		<city/>
		<street>/
	</address>
</person>
```

## 데이터 유효성 검사

---

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%208.png)

- XML 스키마 또는 DTD를 도큐먼트 타입으로 가져올 때 Integration Server 도큐먼트타입의 제약 조건은 자동으로 생성되거나 디자이너에서 수동으로 추가할 수 있습니다.
- 제약 조건은 작은 아이콘으로 시각적으로 인식됩니다.

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%209.png)

위 필드는 필수이지만 "null"일 수 있으며 날짜 형식이어야함을 의미합니다.

## **다음과 같은 방법들로 도큐먼트를 유효성 검사할 수 있습니다:**

- 내장된 유효성 검사 서비스(pub.schema.validate)
- 사용자 지정된 코드로 작성된 유효성 검사 서비스 (자바서비스)
- 입력/출력 탭의 '입력/출력 유효성 검사' 옵션
(이 방법은 오류를 찾고 처리하기가 더 어려우므로 권장되지 않습니다)

**유효성 검사 실습은 따로 포스팅을 해보겠습니다.**

## 도큐먼트를 Output pipeline에서 참조하기

---

![Untitled](/assets/img/2024-01-30-documenttype/Untitled%2010.png)

- 패키지 네비게이터에서 도큐먼트를 드래그하여 로컬 변수 이름을 제공하거나,오른쪽 마우스 버튼을 누른뒤 insert에서 document Reference를 클릭하여 추가할 도큐먼트를 선택합니다.
- 로컬 변수 이름을 제공합니다.
- 새로운 파이프라인 도큐먼트에 적어도 하나의 필드에 값을 설정하지 않으면 파이프라인에서 제거될 수 있으므로 이를 잊지 마세요.

## 마치며

---

wembethods에서 사용하는 객체타입 도큐먼트에 대해서 간략하게 알아보았습니다.

도큐먼트는 앞으로 계속해서 사용하시게 되니 이해가 잘 안되시더라도

계속 사용해보시면 쉽게 이해 되실 것 입니다.

다음 포스팅에서는 간단하게 도큐먼트 유효성검사를 진행해보면서

도큐먼트를 조금 더 이해하실 수 있게 포스팅 해보도록 하겠습니다

감사합니다.