### Redux를 공부해보자!

> Redux는 전역 상태관리 라이브러리다.

[Velog 포스팅](https://velog.io/@jiyaaany/TIL-Redux%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0)

Redux를 사용해 Counter, Todo 상태를 관리해보자.

### 프로젝트 빌드

```
yarn add
yarn start
```

### Ducks 패턴

> 하나의 파일에 action, action 생성 함수, Reducer를 정의하는 패턴

### Presentational and Container
https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0

### useSelector 최적화
redux에서 객체를 가져와야할 경우 `shallowEqual` 함수를 사용해 최적화를 해줘야한다. (권장, 규모가 큰 컴포넌트일 경우 필수)

[사용법]
```
const { number, diff } = useSelector(state => ({
  number: state.counter.number,
  diff: state.counter.diff,
}), **shallowEqual**);
```
위 처럼 state에서 객체를 리턴하는 경우에 `useSelector` 최적화가 권장된다.

또는 아래와 같이 객체를 리턴하지 않고 하나의 상태만 조회하는 방법이 있다.
```
const number = useSelector(state => state.counter.number);
const diff = useSelector(state => state.counter.diff);
```
