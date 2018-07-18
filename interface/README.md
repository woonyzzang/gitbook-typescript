# 인터페이스

**인터페이스**는 JavaScript와 같은 동적 타입 언어 환경에서는 다뤄지지 않았습니다. 하지만 정적 타입 언어인 TypeScript에서는 타입 검사가 요구되므로  인터페이스를 지원합니다. 

인터페이스는 `interface` 키워드를 사용해 다음과 같이 정의합니다.

```typescript
// 인터페이스 Button 정의
interface ButtonInterface {
  onInit():void;
  onClick():void;
}
```

사용자 정의 타입\(Type Alias\)과 유사해보입니다.

```typescript
type ButtonType = {
  onInit():void;
  onClick():void;
}
```

다소 비슷해보이는 것은 사실이나 사용자 정의 타입이 할 수 없는 것을 인터페이스는 할 수 있습니다. 할 수 있는 것 중 하나는 인터페이스는 선언을 병합할 수 있다는 점입니다.

```typescript
interface ButtonInterface {
  onInit():void;
  onClick():void;
}

...

interface ButtonInterface {
  onToggle():void;
}
```

반면 사용자 정의 타입은 선언이 중복되면  오류입니다.

```typescript
type ButtonType = {
  onInit():void;
  onClick():void;
}

// [오류]
// 'ButtonType' 식별자가 중복되었습니다.
type ButtonType = {
  onToggle():void;
}
```

{% embed data="{\"url\":\"https://medium.com/@martin\_hotell/interface-vs-type-alias-in-typescript-2-7-2a8f1777af4c\",\"type\":\"link\",\"title\":\"Interface vs Type alias in TypeScript 2.7\",\"description\":\"The ultimate guide describing differences between interface and type alias for compile time type annotations\",\"icon\":{\"type\":\"icon\",\"url\":\"https://cdn-images-1.medium.com/fit/c/304/304/1\*8I-HPL0bfoIzGied-dzOvA.png\",\"width\":152,\"height\":152,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://cdn-images-1.medium.com/max/1200/1\*c7NX0rtwapsb\_lVRCk1C-A.png\",\"width\":1200,\"height\":648,\"aspectRatio\":0.54},\"caption\":\"인터페이스와 사용자 정의 타입의 차이점을 자세히 다루는 글입니다. 참고하세요.\"}" %}

