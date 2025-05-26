

## 数据库表

### user用户表

| 字段名     | 类型                 | 描述             | 备注             | 索引     |
| ---------- | -------------------- | ---------------- | ---------------- | -------- |
| id         | int                  |                  | 主键约束、自增   | 主键索引 |
| username   | varchar(50)          | 用户名           | 唯一约束         | 唯一索引 |
| password   | varchar(50)          | 密码             |                  |          |
| email      | varchar(100)         | 邮箱             |                  |          |
| avatar_url | varchar(255)         | 头像地址         |                  |          |
| role       | enum('user','admin') | 用户类型         |                  |          |
| created_at | datetime             | 该数据创建的时间 | CURRENT_TIMESAMP |          |



### article文章表

| 字段名      | 类型         | 描述             | 备注             | 索引     |
| ----------- | ------------ | ---------------- | ---------------- | -------- |
| id          | int          |                  | 主键约束、自增   | 主键索引 |
| title       | varchar(200) | 文章标题         |                  |          |
| content     | text         | 文章内容         |                  |          |
| cover_image | varchar(255) | 封面图           |                  |          |
| user_id     | int          | 用户id           | 外键             | 普通索引 |
| category_id | int          | 类别id           | 外键             |          |
| created_at  | datetime     | 该数据创建的时间 | CURRENT_TIMESAMP |          |

### photo摄影作品表

| 字段名        | 类型         | 描述             | 备注             | 索引     |
| ------------- | ------------ | ---------------- | ---------------- | -------- |
| id            | int          |                  | 主键约束、自增   | 主键索引 |
| title         | varchar(200) | 摄影作品标题     |                  |          |
| description   | text         | 作品描述         |                  |          |
| image_url     | varchar(255) | 原图地址         |                  |          |
| thumbnail_url | varchar(255) | 缩略图地址       |                  |          |
| exif_info     | json         | 照片参数等元数据 |                  |          |
| album_id      | int          | 相册表id         | 外键             | 普通索引 |
| user_id       | int          | 用户id           | 外键             | 普通索引 |
| created_at    | datetime     | 该数据创建时间   | CURRENT_TIMESAMP |          |

### album相册表

| 字段名      | 类型         | 描述             | 备注             | 索引     |
| ----------- | ------------ | ---------------- | ---------------- | -------- |
| id          | int          |                  | 主键约束、自增   | 主键索引 |
| name        | varchar(100) | 相册名称         |                  |          |
| description | text         | 相册描述         |                  |          |
| user_id     | int          | 用户id           | 外键             | 普通索引 |
| cover_image | varchar(255) | 封面图           |                  |          |
| created_at  | datetime     | 该数据的创建时间 | CURRENT_TIMESAMP |          |



### category类别表

| 字段名 | 类型        | 描述     | 备注           | 索引 |
| ------ | ----------- | -------- | -------------- | ---- |
| id     | int         | 类别id   | 主键约束、自增 |      |
| name   | varchar(50) | 类别名称 |                |      |

### tag标签表

| 字段名 | 类型        | 描述     | 备注           | 索引 |
| ------ | ----------- | -------- | -------------- | ---- |
| id     | int         | 标签id   | 主键约束、自增 |      |
| name   | varchar(50) | 标签名称 |                |      |

### article_tag文章标签表

| 字段名     | 类型 | 描述   | 备注     | 索引     |
| ---------- | ---- | ------ | -------- | -------- |
| article_id | int  | 文章id | 主键约束 | 主键索引 |
| tag_id     | int  | 标签id | 主键约束 | 主键索引 |

