## **查B站评论网站API文档**
### **网址：https://vicu.online**
### *（自己扒了一下最近那个查B站某用户评论网站的API，整理了一份API文档，可能不是很规范。等后面有时间慢慢把它做成mirai plugin*
——————————————————————————————————————————————————————————
#### **接口地址：https://vicu.online/api/reply**
* 输入参数

| 参数       | 是否必选 | 值类型         | 说明                       |
|----------|------|-------------|--------------------------|
| `uid`    | 必选   | Long        | 用户的UID                   |
| `up_uid` | 可选   | Long        | UP主UID                   |
| `filter` | 可选   | 多个Long，逗号间隔 | UP主过滤器，根据组合筛选出复数个UP主的评论区 |
| `pn`     | 可选   | Int         | 显示的页面序号，不输入时默认只返回第一页                  |
| `sort`   | 可选   | 1或-1        | 时间顺序，1为正序，-1为倒序          |

* 返回值

| 字段              | 类型     | 说明             |
|-----------------|--------|----------------|
| `dynamic_url`   | String | 评论所在链接         |
| `up_uid`        | Long   | UP主UID         |
| `up_uname`      | String | UP主昵称          |
| `replies`       | List   | 评论详情           |
| `content`       | String | 评论内容           |
| `ctime`         | Long   | 评论时间（秒级别时间戳格式） |
|  `like_count`   | Int    | 点赞数            |
| `dynamic_count` | Int    | 该评论区下累计评论数     |

#### **接口地址：https://vicu.online/api/user**
* 输入参数

| 参数    | 是否必选 | 值类型  | 说明    |
|-------|------|------|-------|
| `uid` | 必选   | Long | 用户UID |

*  返回：用户信息

| 字段                 | 类型     | 说明         |
|--------------------|--------|------------|
| `uname`            | String | 用户昵称       |
| `mid`              | Long   | UID        |
| `total`            | Int    | 总评论数       |
| `like_count`       | Int    | 总获赞数       |
| `reply_count`      | Int    | 总被回复数      |
| `first_reply_time` | Long   | 第一次评论时间    |
| `last_reply_count` | Long   | 最后一次评论时间   |
| `item`             | List   | 评论过的UP主列表  |
| `mid`              | Long   | 评论过的UP主UID |
| `uname`            | String | 用户昵称       |
| `total`            | Int    | 总评论数       |


#### **接口地址：https://vicu.online/api/ups**
* 输入参数：无
* 返回：网站支持的UP主

| 字段      | 类型     | 说明    |
|---------|--------|-------|
| `uname` | String | UP主昵称 |
| `mid`   | Long   | UID   |
| `group` | String | 所属组合  |

#### **接口地址：https://vicu.online/api/now/history**
* 输入参数：无
* 返回：最新50条评论、在线人数、总评论数

| 字段            | 类型     | 说明             |
|---------------|--------|----------------|
| `online`      | Int    | 当前在线人数         |
| `total`       | Long   | 总评论数           |
| `dynamic_url` | String | 评论所在链接         |
| `up_uid`      | Long   | UP主UID         |
| `up_uname`    | String | UP主昵称          |
| `mid`         | Long   | 评论者UID         |
| `uname`       | String | 评论者昵称          |
| `content`     | String | 评论内容           |
| `ctime`       | Long   | 评论时间（秒级别时间戳格式） |


### **（PS:有两个参数 `root` 和 `dy_count`还没有搞清楚是用来做什么的）**
