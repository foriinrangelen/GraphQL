## GraphQL 알아보기
### A query language for your API
graphQL은 API용 쿼리 언어이며 GraphQL은 API의 데이터에 대한 이해하기 쉬은 설명을 제공하고 **클라이언트가 필요한것을 정확하게 요청할 수 있는 능력**을 제공한다
![image](https://github.com/foriinrangelen/GraphQL/assets/123726292/b5bae628-de4b-4a0b-b671-63ac41155841)

### REST API 대신 GraphQL을 사용하는이유
#### REST API의 단점
1. 오버 페칭(Over-fetching): REST API에서는 클라이언트가 필요한 데이터만 정확하게 요청하는 것이 불가능하며 하나의 엔드포인트에서 제공하는 모든 데이터를 받아야 하므로, 클라이언트가 필요로 하지 않는 데이터까지도 전송받게 되는 문제가 발생하며 이를 오버 패칭이라고한다
2. 언더 페칭(Under-fetching): 반대로, 클라이언트가 필요한 모든 데이터를 한 번의 요청으로 받아올 수 없는 경우도 있으며 이럴 때 클라이언트는 여러 번의 요청을 보내야 하며, 이는 네트워크 비용 증가와 성능 저하를 초래하게된다 이를 언더 페칭이라고 한다
3. REST API는 엔드포인트를 변경하거나 추가할 때마다 새로운 버전의 API를 만들어야 하는데, 이는 관리 비용을 증가시키고 클라이언트와 서버 간의 호환성 문제를 발생 시킬수있음
#### GraphQL의 장점
1. 스키마를 작성하기때문에 데이터가 어떻게 이루어져 있는지 알수 있다
2. Type을 작성하기 때문에 요청과 응답에 Valid한 데이터가 오고갈 수 있다
3. 아래와 같이 api엔드포인트에 특정 필요한 데이터만 요청해서 받아올 수 있으며 한번의 요청으로 필요한 모든데이터를 받아올 수도 있다
```graphQL
# 1. graphql.org/swapi-graphql
# 2. https://swapi.dev/
{
  starship (starshipID:9){
    name
    model
    length
  }
  species(speciesID:3){
    name
    homeworld {
      gravity
      population
    }
  }
}
```
#### GraphQL의 단점
1. backend에 Schema 및 Type을 정해줘야 하기때문에 생산성이 떨어질수도 있다
2. REST API보다 데이터를 캐싱하는게 까다롭다
3. 개발자가 GraphQL쓰는법을 따로 배워야한다
