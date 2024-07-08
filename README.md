# 과제 (V1)

### 개요

리액트와 타입스크립트를 활용해서 명세대로 간단한 투두리스트를 만들어본다. 

### 디자인
[피그마 링크 확인](https://www.figma.com/design/cgH0Ev7k0muNt0lB3dSowC/Untitled?node-id=0-1&t=GgTy7yMRBVMrmLZr-1)

### 기본 과제
1. 검색창에 추가하면 메모가 추가되도록 해보기
2. 메모들의 우측상단의 버튼을 누르면 삭제버튼이 보인다. 한번 더 누르면 삭제 버튼이 사라진다.
3. 삭제버튼을 누르면 메모가 삭제된다.
4. 메모의 저장은 localstotrage를 활용한다. 

### 추가 과제1
메모 localstroage에 저장하는 대신에 서버와 통신해서 가져와보자. 서버 url은 개인 문의 부탁

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
1. 메모의 버튼을 누르면 상세보기 페이지로 이동한다. 
2. 이때 react-router-dom을 사용해서. 상세보기 페이지로 이동이 되도록 한다.
