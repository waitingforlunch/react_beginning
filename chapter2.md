```
<html lang="en">
<body>
    <div id="root"></div>
</body>
<script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<script type="text/babel">
    const root = document.getElementById("root");
    const Title = () => (
        <h3 id="title" onMouseEnter={() => console.log("mounse enter")}>
         Hello I'm a title
        </h3>
        );
    // const h3 = React.createElement("h3", {
    //     onMouseEnter: () => console.log("mounse enter"),
    // }, "Hello I'm a span");
    const Button = () => (
        <button id="btn" onClick={() => console.log("im clicked")}>
            Click me
        </button>
    );
    
    // const btn = React.createElement("button", {
    //     onClick: () => console.log("im clicked"),
    // }, "Click me");
    // const container = React.createElement("div", null, [Title, btn]);
    const Container = () => ( 
        <div>
            <Title/>
            <Button/>
            <Title/>
        </div> 
    );
    ReactDOM.render(<Container />, root);
</script>
</html>
```
이게 뭐냐하면 
일단 html 자체에는 <div id="root"></div> 이거 하나밖에 안쓰고, 나머지 element는 리액트로 써주는것!!!   

1. 그래서 const root = document.getElementById("root"); 얘는 root 그냥 가져오고   
2. Title 이라는 변수를 만듬 --> 여기서 () => 이런식으로 있는건 그냥 리턴만해주는 함수를 쓰고 싶을떄 쉽게 쓰는 방법임 
- 리액트 Jsx가 좋아서 저렇게 변수 안에다가 html처럼 태그 추가하고, 이벤트 같은 property넣고, 컨텐츠도 추가 가능     
const Title = () => (
        <h3 id="title" onMouseEnter={() => console.log("mounse enter")}>
         Hello I'm a title
        </h3>
        );   
3. Button 도 마찬가지로 만들어줌   
const Button = () => (
        <button id="btn" onClick={() => console.log("im clicked")}>
            Click me
        </button>   
4. 그리고 Container 라는 변수를 만들고 여기선 div태그를 생성. 그리고 Container 안에 2,3번의 Title, Button 을 넣어준다는말임.   
- 여기서 중요한건 <Title/> <Button/> 처럼 안에는 함수만 들어갈 수 있음. 그래서 위에서도 다 함수로 만든거고   
- 얘네는 무조건 대문자로 시작해야됨 그래야 리액트가 얘네가 이 변수라는걸 알아차림. 막 button으로 하면 html태그라고 인식할수있으니 조심.    
5. 마지막으로, ReactDOM.render(<Container />, root); 라는건 아까 1번의 root안에 Container를 넣겠다는 뜻.

*이 건 babel?이라는 변환 프로그램..? 을 쓰는거임 그래서 맨 위에 script type="text/babel" 추가. 






