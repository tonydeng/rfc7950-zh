# 7. `YANG`声明

本章节描述了所有的`YANG`语句声明。

请注意，即使是`YANG`中定义的没有任何子语句的声明，也可以使用供应商自行扩展的子语句。 例如，“`description`”语句没有在`YANG`中定义的任何子语句，但是下面的用法是合法的：

```YANG
description "Some text." {
  ex:documentation-flag 5;
}
```
