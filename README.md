# html-practice
html/css 연습한 내용을 정리

## px, %, em, rem
1. px : 사용자의 화면 크기에 비례되서 값이 적용된다.
2. % : 부모 태그의 크기에 비례되서 크기가 적용된다.
3. em : `자신이 원래 받았던 폰트사이즈`에 비례되서 적용된다.
4. rem : `문서의 기본값`에 비례해서 적용된다.
5. v : 뷰 포트(현재 클라이언트 화면)에 비례해서 적용한다.

5. 기타
    - body의 기본 px은 `16px`이다.(문서의 기본값)
    - 문서의 기본은 root이므로 root의 폰트사이즈를 변경하면 전체 기본 폰트사이즈를 변경할 수 있다.
      ```
        :root {
           font-size: 12px;
      }
      ```
      
## text style
1. font-size : 글자 크기
   - medium : 16px
   - large
   - small
   - em,rem,px 등으로 설정할 수 있다.
2. font-weight : 글자 굵기
   - normal : 기본값
   - lighter : 얇게
   - bord : 굴게
   - 직접 지정 : ex)100~900까지 설정가능
3. test-decoration : 글자 밑줄
   - underline,overline : 말 그대로 상하단에 밑줄을 긋는다.
   - line-throw : 문자 가운데 줄을 긋는다. ex) 가격할인, 수정
4. font-style : 글자 스타일
   - normal : 기본값
   - italic / oblique: 기울여서
5. test-align : 글자 정렬
   - left : 왼쪽 정렬
   - right  오른쪽 정렬
   - center : 가운데 정렬
   - 태그의 성격이 `inline` 때는 왼쪽 정렬로 되어있다.
6. spacing : 글자 간격
   - letter-spacing : 글자간 간격 
   - word-spacing : 단어간 간격
   - line-height : 라인 윗 부분에 높이를 넣는다.ex) 박스안에서 글자를 세로 가운데 정렬
      - 부모의 높이의 절반 만큼 적용하면, 해당 태그는 가운데 위치시킬 수 있다.
7. text-transform : 글자 변형
   - vertical-align : 글자의 높낮이를 변형, `img 하단에 빈공간을 제거할 때 top을 넣어 제거`
   - text-align : 글자 쏠림
      - justify : 워드에서 글자 `균할분등`에 해당, 문장을 전체에 균등하게 뿌리도록 한다.
   - word-break : 문장의 단어를 기준으로 줄바꿈이 이루어지지만, 해당 속성을 이용하면 글자단위로 줄바뀜
8. white-pace :
   - nowrap : 글자가 지정된 공간이 넘어도, 줄바꿈을 하지 않는다.
   - pre : <pre> 태그와 같은 기능, 실제 테스트의 줄바꿈 스페이스를 그대로 적용, warp 속성을 무시
   - pre-wrap : pre + wrap
   - pre-line : pre + line
   - nowrap 정도가 쓰이며, 다른건 거의 사용되지 않는다. 
9. test-ident : 들여쓰기 : 라인에서 글자 시작위치를 조절(px,rem...) 

## Display

1. inline : 자신이 갖고 있는 너비,높이만 사용, 글씨와 같은 성격을 갖는다. 
   - height 속성 무시
2. block : 자신에게 지정된 너비,높이를 모두 사용, `세로 한줄을 전부 사용`
3. inline-block : 크기속성과 글씨 속성을 갖는다.
   - `글씨처럼 취급`되면서 동시에 `height` 도 적용된다.
4. hidden : 적용된 대상을 숨긴다.
5. none : html자체를 그리지 않는다. 빈공간 조차 주지 않는다.
6. visibility : 공간은 배정하지만 보이지는 않는다.
7. overflow 
   - hidden : 해당 태그에 배정된 `텍스트가 초과`한다면 출력하지 않는다.
   - scroll : 텍스트가 초과된다면 세로로 `스크롤`을 만들어준다.넘치지 않는 방향에도 만들어준다.
   - auto : 넘치는 방향에만 스크롤을 만들어준다. -> 회원약관 등에서 사용할 수 있다.

## background
1. background-image : 이미지를 불러온다.
   ```aidl
       {
      background-image:url('${image_location}');
   }
   ```
2. background-repeat :
   - repeat : default
   - no-repeat :
3. background-position : 불러온 이미지를 기준으로 위치를 배정한다.
   ```aidl
      {
       background-position : right top;
       background-position : 50% 50%;
    // left right center top bottom N%
   }
   ```
4. 상위 3가지 속성은 background에 단일 속성으로 정의할 수 있다.

## board 
외부 테두리 ,요소에 다른 설정을 하지 않는다면, border까지의 합이 전체 길이 너비가 된다.
```aidl
   {
      border : ${px} // 상 우 하 좌, 상하 좌우, 상 좌우 상하
      border-color : ${color}
      border-radius : ${px} // 1:시계방향, 2:상하,좌우,3개:좌상 우상좌하 우하
      // 150px, 50%를 적용하면 원(circle)이 된다.
   }
```
## padding
element 부터 border 까지의 거리!

## margin
다른 엘리멘트와의 거리, 두 엘리멘트의 거리는 margin + margin(X), 둘 중 가장 큰 margin (O), 즉 `중첩`된다!
1. `margin`을 상하 = 0, 좌우 = auto를 설정하면 엘리멘트를 가운데 위치시킬 수 있다. 

## box-sizing
1. box-sizing: `content-box` = 요소의 사이즈 = element size + border + padding(default)
2. box-sizing: `border-box` = element size + border size

## float
1. float 이 적용되면 다음에 오는 엘리멘트들이 적용된 엘리멘트를 감쌀 수 있다.
2. 다음에 오는 엘리멘트들이 flot의 영향을 받지 않게 하려면 `clear:${float의방향}`을 추가한다. `both`를 사용하는게 깔끔하다.
3. 연속으로 나열된 엘리멘트들이 float이 적용되었다면 마지막에 꼭 float을 해제시키는 코드를 넣어야한다.
   ```aidl
      .supper:after { // super : float이 적용된 엘리멘트를 담고 있는 엘리멘트
        content : '' // 빈문자열
        clear:both  // float 해제
        display: block // inline(X), block(O)
   }
   ```
4. 자식요소에 float을 적용하면 부모요소의 height, background 는 무시된다. 그러므로 3번의 float 해제를 꼭 해야한다.

## position
default = static 
1. `position : absolute` :
   - 적용된 요소는 붕 뜬다 -> 다른 요소와 중첩될 수 있다.
   - 내부 컨테츠 만큼 크기가 줄어든다.
   - `부모 요소를 기준`으로 위치하며, 부모가 따로 없다면 최고 조상인 html까지 올라간다.
   ```aidl
      {
      position : absolute;
      left : x px;
      right : x px;
      top : x px;
      bottom : x px;
   }
   ```
   - 가장 가까운 position이 적용된 조상 엘리먼트를 기준으로 위치를 잡는다.(static이 아닌 엘리멘트!)
   
2. `position : relative` :
   - 자기 자신을 기준으로 위치를 정한다.
   - 위치에 대한 값을 지정하지 않는다면 본인이 배정받은 위치에 위치한다 -> 적용해도 변화가 없다
   - 자신에게 원래 `배정된 자리`에서 부터 포지션을 이동
   - 해당 엘리멘트만 옮겨서 겹쳐야하는 상황이 아니라면 `margin`을 사용한다.
   - 자식 엘리멘트의 기준값이 되고 싶다면 `relative`를  적용한다.

3. `position : fixed` : 
   - 무조건 화면을 기준으로 위치를 잡는다.
   
## transition
1. transition-property : 보여지는 속성 
2. transition-duration : 전환되는 시간 
3. transition-delay : 변화가 시작되기까지의 지연시간
4. transition-timing-function
   - ease : 느리다가 빠르게
   - 
5. transition : ${property:all} ${duration} ${delay} ${function} : 한줄에 정의 가능하다
   - `property`에 `all`을 넣어 모든 속성을 선택할 수도 있다.
6. 관련 자료 및 동영상
   - [유튜브](https://www.youtube.com/watch?v=D0kjVLrrKPs&list=PL-qMANrofLyvQ6FuaIe3YRRX82eISDy11&index=83)
   
## flex
| 속성 | 설명 |빈도|
|---|:---:|---:|
|display:flex|자식요소를 `블록 수준` 플렉서 박스로 이동하게 한다.|자주|
|display:inline-flex|자식요소를 `인라인 수준` 플렉서 박스로 이동하게 한다.|적다|

|속성|설명|
|---|:---:|
|flex-decoration : row|박스를 왼에서 오른쪽,주축은 가로,교차추축은 세로(default)|
|flex-decoration : row-reverse|박스를 가로로 배치하되, 역방향으로 배치|
|flex-decoration : column|박스를 위에서 아래로 배치, 주축은 세로 교차축은 세로가 된다.|
|flex-decoration : column-reverse|박스를 위에서 아래로 배치, 역방향으로 배치|
1. flex-direction
   - row : 가로로 자식요소를 쌓는다.
   - column : 세로로 자식요소를 쌓는다.
2. flex-flow : 주축을 기준으로 위치를 잡는다.
   - wrap : 자식요소가 해딩 방향의 최대 길이를 초과할 경우 쌓는다.
   - nowrap : 자식요소가 해딩 방향의 최대 길이를 초과해도 쌓지 않는다.
3. justify-content
   - space-between
   - space-around
   - space-evenly
   - flex-first
   - flex-end
4. align-items : 교차축을 기준으로 위치를 잡는다.
   - center
   - stretch : 기본값, 늘린다!
   - flex-first/end : 교차축의 시작/끝을 기준으로
   - baseline : 글자의 베이스 라인을 기준으로 잡는다.
   - 자식 엘리멘트에게 직접 `align-self:${attribute}`를 사용해서 개별로 교차축을 설정할 수 있다.
5. align-content : justify-content와 같지만 교차축을 기준으로 한다.
6. flex : 배치될 엘리멘트에 적용하는 속성, flex가 정의된 부모요소에서 얼만큼 크기를 차지할지 설정
## 기타 팁
1. 이미지 밑에 여백 제거 : `vertical-align:top;`
2. [서브메뉴바](https://www.youtube.com/watch?v=D0kjVLrrKPs&list=PL-qMANrofLyvQ6FuaIe3YRRX82eISDy11&index=83)

## 유용한 사이트
1. 