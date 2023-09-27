# basic-command
> 마크다운 문법 학습 


## Heading
  - `# H1` 
  - `## H2`
  - `### H3`
  - `#### H4`
    - # H1 
    - ## H2 
    - ### H3
    - #### H4


## Bold
- `**bold text**` 
    - **bold text**


## Italic
- `*italicized text*`
    - *italicized text*


## Blockquote
- `> blockquote`
    - > blockquote


## Ordered List
- `1. First item`
- `2. Second item`
- `3. Third item`
    1. First item
    2. Second item
    3. Third item
- 하위항목 생성 시 tab 이용하여 들여쓰기


## Unordered List
- `- First item`
- `- Second item`
- `- Third item`
    - First item
    - Second item
    - Third item
- 하위항목 생성 시 tab 이용하여 들여쓰기


## Code
- `'code'`
    - `code`


## Horizontal Rule
- `---`
    - ---


## Link
- `[title](https://www.example.com)`
    - [title](https://www.example.com)
- eg. `[github](https://github.com)`
    - [github](https://github.com)


## Image
- 1. `![alt text](<이미지주소복사+붙여넣기>)`
- 2. `![alt text](<이미지저장경로>)`
- 이때 이미지 확장자는 `.jpg/.jpeg` 가 아닐 경우 오류 발생 가능

    - 1. ![Kiss by Klimt](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRlj3bCd7LFRKL7Pq723ZAVve9f7ovEHgNmpw&usqp=CAU)  
    - 2. ![Kiss by Klimt](./assets/images.jpeg)


## Fenced Code Block
- ` ``` contents ``` `

```python
def func():
    return True
```

```javascript
console.log('hello')
```