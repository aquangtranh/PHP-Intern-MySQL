#Câu 1: Tạo database như hình trên (sau khi tạo thì import database, sẽ gửi )
- Tạo database:
`
```
  CREATE DATABASE mysql_exercise;
```
- Tạo bảng:

  + Bảng user:
```
  CREATE TABLE user (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    full_name     VARCHAR(255) NOT NULL,
    email         VARCHAR(255) NOT NULL,
    rank          TINYINT(4) NOT NULL,
    is_active     TINYINT(1) NULL,
    created_at    TIMESTAMP NULL,
    PRIMARY KEY (id)
  );
```
  + Bảng category:

```
  CREATE TABLE category (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    title         VARCHAR(255) NOT NULL,
    description   VARCHAR(255) NULL,
    PRIMARY KEY (id)
  );
```
  + Bảng comment: 
```
  CREATE TABLE comment (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    target_table  VARCHAR(20) NOT NULL,
    target_id     INT(11) NOT NULL,
    user_id       INT(11) NOT NULL,
    comment       TEXT NULL,
    created_at    TIMESTAMP NULL,
    updated_at    TIMESTAMP NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (user_id) REFERENCES user(id)
  );
```

  + Bảng blog:
```
  CREATE TABLE blog (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    category_id   INT(11) NOT NULL,
    user_id       INT(11) NOT NULL,
    title         VARCHAR(255) NOT NULL,
    view          INT(11) NOT NULL,
    is_active     TINYINT(1) NULL,
    content       TEXT NULL,
    created_at    TIMESTAMP NULL,
    updated_at    TIMESTAMP NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (category_id) REFERENCES category(id),
    FOREIGN KEY (user_id) REFERENCES user(id)
  );

```
  + Bảng news:
```
  CREATE TABLE news (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    category_id   INT(11) NOT NULL,
    title         VARCHAR(255) NOT NULL,
    view          INT(11) NOT NULL,
    is_active     TINYINT(1) NULL,
    content       TEXT NULL,
    created_at    TIMESTAMP NULL,
    updated_at    TIMESTAMP NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (category_id) REFERENCES category(id)
  );
```
  + Bảng follow:
```
  CREATE TABLE follow (
    id            INT(11) NOT NULL AUTO_INCREMENT,
    from_user_id  INT(11) NOT NULL,
    to_user_id    INT(11) NOT NULL,
    created_at    TIMESTAMP NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (from_user_id) REFERENCES user(id),
    FOREIGN KEY (to_user_id) REFERENCES user(id)
  );
```
  