# 7. `YANG`声明

以下部分描述了所有的`YANG`语句。

请注意，即使是没有在`YANG`中定义的任何子语句的语句，也可以使用特定于供应商的扩展名作为子语句。 例如，“`description`”语句没有在`YANG`中定义的任何子语句，但是下面是合法的：

```YANG
description "Some text." {
  ex:documentation-flag 5;
}
```
