# go-zero-template

## 说明

这里存放 go-zero 的模板文件，主要是修改了 is_deleted 的字段，如下。

```sql
CREATE TABLE IF NOT EXISTS `article_type` (
  `id` BIGINT NOT NULL AUTO_INCREMENT COMMENT 'id',
  `code` VARCHAR(255) NOT NULL COMMENT 'primary key',
  `name` VARCHAR(255) NOT NULL DEFAULT '' COMMENT '类型',
  `created_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `updated_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  -- is_deleted 字段
  `is_deleted` TINYINT NOT NULL DEFAULT 0 COMMENT '0:未删除 1:已删除',
  UNIQUE KEY `uk_code` (`code`),
  PRIMARY KEY (`id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb4 COMMENT = '文章类型表';
```
