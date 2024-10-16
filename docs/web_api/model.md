### Charts 图表信息

```
{
    "chartName": "string",
    "classification": "string",
    "data": "string",
    "addition": -1
}
```

#### 属性：

- **chartName** - 图表名称。
- **classification** - 图表分类，默认为"0"。
- **data** - 图表的数据信息。
- **addition** - 额外参数，默认为-1。

#### 说明：

- `chartName` 和 `data` 是构造图表的必要参数。
- 可以选择通过指定 `classification` 和 `addition` 进一步分类或添加额外信息。

------

### Recruitment 招聘信息

```
{
    "id": 0,
    "position": "string",
    "company": "string",
    "salary": "string",
    "location": "string",
    "qualification": "string",
    "experience": "string",
    "businessNature": "string",
    "detailPage": "string",
    "jobDescription": "string"
}
```

#### 属性：

- **id** - 招聘信息 ID。
- **position** - 职位名称。
- **company** - 公司名称。
- **salary** - 工资水平。
- **location** - 工作地点。
- **qualification** - 资历要求。
- **experience** - 工作经验要求。
- **businessNature** - 企业性质。
- **detailPage** - 详情页面链接。
- **jobDescription** - 工作描述。

#### 说明：

- 招聘信息包含职位、公司、薪水等关键信息。
- 通过 `detailPage` 可以访问更详细的职位信息页面。

------

### RecruitmentInformation 招聘详情信息

```
{
    "position": "string",
    "company": "string",
    "slavery": "string",
    "location": "string",
    "workExperience": "string",
    "qualification": "string",
    "businessNature": "string",
    "scale": "string",
    "detailPage": "string",
    "recruitNumber": "string",
    "jobDescription": "string",
    "field": "string",
    "valid": "1"
}
```

#### 属性：

- **position** - 职位名称。
- **company** - 公司名称。
- **slavery** - 薪资待遇。
- **location** - 工作地点。
- **workExperience** - 工作经验要求。
- **qualification** - 资历要求。
- **businessNature** - 企业性质。
- **scale** - 公司规模。
- **detailPage** - 详情页面链接。
- **recruitNumber** - 招聘人数。
- **jobDescription** - 工作描述。
- **field** - 工作领域。
- **valid** - 有效性标识，默认值为"1"。

#### 说明：

- `RecruitmentInformation` 提供更详细的招聘信息，包括公司规模和招聘人数等。
- 通过 `valid` 字段标识招聘信息是否有效。

### Result 结果信息

```
{
    "code": 200,
    "msg": "string",
    "data": {}
}
```

#### 属性：

- **code** - 状态码，200 表示成功，0 表示错误。
- **msg** - 返回信息，成功时为 "success"，错误时为错误描述。
- **data** - 返回的具体数据对象，可以为任意类型。

#### 方法：

- `success()` - 返回默认成功结果（`msg` 为 "success"，`data` 为 `null`）。
- `success(Object data)` - 返回带数据的成功结果。
- `error(String msg)` - 返回带错误信息的错误结果，`data` 为 `null`。
- `error(String msg, Object data)` - 返回带数据和错误信息的错误结果。

------

### Sentence 句子信息

```
{
    "classification": "string",
    "text": "string"
}
```

#### 属性：

- **classification** - 句子的分类标签。
- **text** - 句子的内容文本。

#### 说明：

- `Sentence` 用于存储分类后的文本句子，可用于各种自然语言处理任务。

------

### TaggedInformation 标签信息

```
{
    "id": 0,
    "qualification": 0,
    "salary": 0,
    "location": 0,
    "businessNature": 0,
    "field": 0,
    "workExperience": 0,
    "actual_salary": 0,
    "sixNum": 0,
    "fiveNum": 0
}
```

#### 属性：

- **id** - 标签信息的 ID。
- **qualification** - 资历评分。
- **salary** - 工资评分。
- **location** - 工作地点评分。
- **businessNature** - 企业性质评分。
- **field** - 工作领域评分。
- **workExperience** - 工作经验评分。
- **actual_salary** - 实际工资评分。
- **sixNum** - 六级评分标准。
- **fiveNum** - 五级评分标准。

#### 说明：

- `TaggedInformation` 用于存储不同分类项的评分，帮助分析职位或招聘信息中的各项内容。

------

### User 用户信息

```
json复制代码{
    "userId": 0,
    "username": "string",
    "password": "string",
    "accountName": "string"
}
```

#### 属性：

- **userId** - 用户 ID。
- **username** - 用户名，登录时使用。
- **password** - 用户密码。
- **accountName** - 用户账户名称，显示为用户的昵称。

#### 说明：

- 用户对象包含登录凭据和展示名称。根据需求可以带有 `userId` 或不带，支持不同构造方法。