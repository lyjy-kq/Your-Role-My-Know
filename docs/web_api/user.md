## 基础 URL

```
/user
```

## 接口

### 1. **用户注册**

用户注册一个新账号。

- **URL**: `/register`

- **方法**: `POST`

- **描述**: 该接口允许用户通过提供 `用户名` 和 `密码` 来注册新账号。如果注册成功，将返回成功响应；如果账号或用户名已存在，则返回错误信息。

- 请求参数

  - **username** (字符串, 必填): 新账号的用户名。
  - **password** (字符串, 必填): 新账号的密码。

- 请求示例

  ```
  curl -X POST "http://{服务器地址}/user/register" -d "username=zhangsan&password=mima123"
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": "用户注册成功"
      }
      ```

  - 错误响应

    - **状态码**: 400 Bad Request

    - 响应体

      ```
      {
        "code": 400,
        "message": "账号或用户名已存在"
      }
      ```

### 2. **用户登录**

用户登录现有账号。

- **URL**: `/login`

- **方法**: `POST`

- **描述**: 该接口允许用户通过提供 `用户名` 和 `密码` 进行登录。如果登录成功，将返回成功响应；如果账号或密码错误，将返回错误信息。

- 请求参数

  - **username** (字符串, 必填): 用户名。
  - **password** (字符串, 必填): 账号密码。

- 请求示例

  ```
  curl -X POST "http://{服务器地址}/user/login" -d "username=zhangsan&password=mima123"
  ```

- 响应

  - 成功响应

    - **状态码**: 200 OK

    - 响应体

      ```
      {
        "code": 200,
        "message": "success",
        "data": "登录成功"
      }
      ```

  - 错误响应

    - **状态码**: 400 Bad Request

    - 响应体

      ```
      json复制代码{
        "code": 400,
        "message": "账号或密码错误"
      }
      ```