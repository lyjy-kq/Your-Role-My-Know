### 1. **获取建议**

根据用户输入的文本生成相应的建议或响应。

- **URL**: `/advice`

- **方法**: `POST`

- **描述**: 接收用户输入的文本，调用模型生成建议或响应。如果文本为空，则返回错误信息。如果生成成功，则返回建议；如果文本无效或没有匹配结果，返回错误信息。

- 请求参数

  - 请求体

     (JSON):

    - **text** (字符串, 必填): 用户输入的文本。

- 请求示例

  ```
  curl -X POST "http://{服务器地址}/advice" \
  -H "Content-Type: application/json" \
  -d '{"text": "如何提高编程技能？"}'
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": "多练习，学习新的编程语言，阅读源码"
      }
      ```

  - 错误响应

    - 文本为空错误

      - **状态码**: 400 Bad Request

      - 响应体

        ```
        {
          "code": 400,
          "message": "文本不能为空"
        }
        ```

    - 无效消息错误

      - **状态码**: 400 Bad Request

      - 响应体

        ```
        {
          "code": 400,
          "message": "消息无效或无匹配结果"
        }
        ```

### 2. **生成图表**

根据输入的标签信息生成相关的图表。

- **URL**: `/all`

- **方法**: `POST`

- **描述**: 根据 `TaggedInformation` 数据生成图表。

- 请求参数

  - 请求体

     (JSON):

    - **taggedInformation** (对象, 必填): 包含标签信息的对象。

- 请求示例

  ```
  curl -X POST "http://{服务器地址}/all" \
  -H "Content-Type: application/json" \
  -d '{"tagName": "技术", "tagId": 1}'
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": { ... }  // 返回生成的图表数据
      }
      ```

  - 错误响应

    - **状态码**: 400 Bad Request

    - 响应体

      ```
      {
        "code": 400,
        "message": "图表生成失败"
      }
      ```

### 3. **获取描述信息**

获取所有相关的描述信息。

- **URL**: `/getDescription`

- **方法**: `GET`

- **描述**: 获取所有存储的描述信息。

- **请求参数**: 无

- 请求示例

  ```
  
  curl -X GET "http://{服务器地址}/getDescription"
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": [
          {
            "sentenceId": 1,
            "content": "描述内容1"
          },
          {
            "sentenceId": 2,
            "content": "描述内容2"
          }
        ]
      }
      ```

  - 错误响应

    - **状态码**: 400 Bad Request

    - 响应体

      ```
      {
        "code": 400,
        "message": "数据返回失败"
      }
      ```

### 4. **获取公司描述**

根据公司类型获取对应的描述信息。

- **URL**: `/companydescription`

- **方法**: `POST`

- **描述**: 根据公司类型 `type` 获取对应的描述信息。

- 请求参数

  - **`type`** (整型, 必填): 公司类型标识符。

- 请求示例

  ```
  
  curl -X POST "http://{服务器地址}/companydescription?type=1"
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": [
          {
            "sentenceId": 1,
            "content": "公司描述1"
          },
          {
            "sentenceId": 2,
            "content": "公司描述2"
          }
        ]
      }
      ```

  - 错误响应

    - **状态码**: 400 Bad Request

    - 响应体

      ```
      {
        "code": 400,
        "message": "数据返回失败"
      }
      ```