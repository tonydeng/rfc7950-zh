# 15. 与`YANG`相关的错误的`NETCONF`错误响应

定义了一些与数据模型处理有关的错误情况的`NETCONF`错误响应。 如果相关的`YANG`语句有一个“`error-app-tag`”子语句，则覆盖下面指定的默认值。


## 15.1. 违反“`unique`”声明的数据的错误消息

如果一个`NETCONF`操作会导致一个“`unique`”约束失效的配置数据，则必须返回以下错误：

```YANG
error-tag:      operation-failed
error-app-tag:  data-not-unique
error-info:     <non-unique>: Contains an instance identifier that points to a leaf that invalidates the "unique" constraint.  This element is present once for each non-unique leaf.
                The <non-unique> element is in the YANG namespace ("urn:ietf:params:xml:ns:yang:1").
```

## 15.2. 违反“`max-elements`”语句的数据的错误消息

如果一个`NETCONF`操作会导致一个列表或一个叶子列表中的条目太多的配置数据，则必须返回以下错误：

```
error-tag:      operation-failed
error-app-tag:  too-many-elements
```

即使存在多个额外的子项，该错误也会返回一次，错误路径将标识列表节点。

## 15.3. 违反“`min-elements`”声明的数据的错误信息

如果一个`NETCONF`操作会导致一个列表或一个叶子列表的条目太少的配置数据，则必须返回以下错误：

```YANG
error-tag:      operation-failed
error-app-tag:  too-few-elements
```

这个错误被返回一次，错误路径标识列表节点，即使有多个子节点丢失。

## 15.4. 违反“`must`”声明的数据的错误消息

如果`NETCONF`操作会导致违反“`must`”语句的配置数据，则必须返回以下错误，除非“`must`”语句存在特定的“`error-app-tag`”子语句。

```YANG
error-tag:      operation-failed
error-app-tag:  must-violation
```

## 15.5. 针对违反“`require-instance`”声明的数据的错误消息

如果`NETCONF`操作会导致配置数据，其中标有`require-instance`“`true`”的“`instance-identifier`”或“`leafref`”类型的叶片指的是不存在的实例，则必须返回以下错误：

```YANG
error-tag:      data-missing
error-app-tag:  instance-required
error-path:     Path to the instance-identifier or leafref leaf.
```

## 15.6. 违反强制性“`choice`”声明的数据的错误消息

如果一个`NETCONF`操作会导致配置数据，在强制选项中不存在节点，则必须返回以下错误：

```YANG
error-tag:      data-missing
error-app-tag:  missing-choice
error-path:     Path to the element with the missing choice.
error-info:     <missing-choice>: Contains the name of the missing
                mandatory choice.

                The <missing-choice> element is in the YANG
                namespace ("urn:ietf:params:xml:ns:yang:1").
```

## 15.7. “`insert`”操作的错误消息

如果在列表或叶列表节点的`<edit-config>`中使用了“`insert`”和“`key`”或“`value`”属性，并且“`key`”或“`value`”引用了不存在的实例，必须返回以下错误：

```YANG
error-tag:      bad-attribute
error-app-tag:  missing-instance
```
