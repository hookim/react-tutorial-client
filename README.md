# 과제 (V1)

### 개요

리액트를 활용해서 명세대로 간단한 투두리스트를 만들어본다. 

### 디자인
[피그마 링크 확인](https://www.figma.com/design/cgH0Ev7k0muNt0lB3dSowC/Untitled?node-id=0-1&t=GgTy7yMRBVMrmLZr-1)

### 기본 과제
1. 검색창에 글을 검색하고 추가하면 메모가 추가되도록 해보기
2. 메모들의 우측상단의 버튼을 누르면 삭제버튼이 보인다. 한번 더 누르면 삭제 버튼이 사라진다.
3. 삭제버튼을 누르면 메모가 삭제된다.
4. memo의 저장은 localstorage를 활용해서 저장할 수 있다. 

목표
1. 컴포넌트간 데이터를 전달할 수 있다.
2. 삭제버튼의 visibility를 관리하기 위해서 useState hook을 사용할 수 있다. 
3. 간단한 webstorage API(localstorage)를 활용해볼 수 있다.    

### 추가 과제1
메모데이터를 localstroage에 저장하는 대신에 서버의 db에 저장해보고 가져와 보자. api는 아래 참조 부탁. 그리고 서버 base url은 개인 문의 부탁

목표
1. 서버와 통신하면서 비동기 처리를 이해할 수 있다.
2. 컴포넌트의 라이프 사이클을 이해할 수 있다. 
3. 함수형 컴포넌트에서 useEffect hook을 사용할 수 있다.
4. .env에 안전하게 base url정보를 저장할 수 있다. 

#### api 
1. `GET` `/api/v1/memos`
    
    response 

    ```json
    {
        "data": [
            {
                "content": "포스트맨에서 작성해봅니다.",
                "createdAt": "2024. 7. 5.",
                "id": "971cb97f-5a92-4e31-8a27-5a0d2944f3b5"
            }
        ]
    }
    ```
    
2. `POST` `/api/v1/creatememo`
    
    body parameter
    
    ```json
    {
        "content" : "메모내용을 남겨보자"
    }
    ```

    response 

    ```json
        true
    ```

3. `POST` `/api/v1/deletememo`

    body parameter

    ```json
    {
        "id" : "971cb97f-5a92-4e31-8a27-5a0d2944f3b5"
    }
    ```

    response 

    ```json
        true
    ```

4. `공통 에러 코드`

    - 400
        ```json
        {
            'message' : '유효하지 않은 값입니다.'
        }
        ```

    - 500
        ```
        {
            'message' : '서버 오류입니다. 잠시후에 시도해주세요.'
        }
        ```

### 추가 과제2
메모의 버튼을 누르면 상세보기 페이지로 이동한다. 

목표
1. 클라이언트 사이드 라우팅기술을 이해할 수 있다.
2. 이를 위해 react-router-dom라이브러리를 활용할 수 있다. 


### 주의사항
cors에러 방지를 위해 프론트 페이지 주소는 http://localhost:5173으로 유지해주세요. 
