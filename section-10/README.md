# 10. `XPath`函数

本文档定义了两个通用的`XPath`函数和五个YANG类型特定的XPath函数。 函数签名用[[XPATH](https://tools.ietf.org/html/rfc7950#ref-XPATH)]中使用的语法指定。

## 10.1. 节点集函数

### 10.1.1. `current()`

```XPath
node-set current()
```

`current()`函数不接受任何输入参数，并返回以初始上下文节点为唯一成员的节点集。

### 10.1.2. 使用示例

现在有一个列表

```YANG
list interface {
  key "name";
  ...
  leaf enabled {
    type boolean;
  }
  ...
}
```

以下叶定义了一个“`must`”表达式，确保引用的接口被启用：

```YANG
leaf outgoing-interface {
  type leafref {
    path "/interface/name";
  }
  must '/interface[name=current()]/enabled = "true"';
}
```

## 10.2. 字符串函数

### 10.2.1. `re-match()`

```XPath
boolean re-match(string subject, string pattern)
```

如果“`subject`”字符串匹配正则表达式“`pattern`”，则`re-match()`函数返回“`true`”。 否则，返回“`false`”。

`re-match()`函数检查字符串是否与给定的正则表达式匹配。 使用的正则表达式是`XML`模式正则表达式[[XSD-TYPES](https://tools.ietf.org/html/rfc7950#ref-XSD-TYPES)]。 请注意，这包括正则表达式在头部和尾部的隐式锚定。

#### 10.2.1.1. 使用示例

表达式如下：

```XPath
re-match("1.22.333", "\d{1,3}\.\d{1,3}\.\d{1,3}")
```

返回“`true`”。

要计算所有名为`eth0`。`<number>`的逻辑接口，请执行以下操作：

```XPath
count(/interface[re-match(name, "eth0\.\d+")])
```

## 10.3. `YANG`类型“`leafref`”和“`instance-identifier"`”的函数

### 10.3.1. `deref()`

```XPath
node-set deref(node-set nodes)
```

`deref()`函数遵循第一个节点在参数“`nodes`”中以文档顺序定义的引用，并返回它引用的节点。

如果第一个参数节点的类型是“`instance-identifier`”，则该函数返回一个包含实例标识符引用的单个节点（如果存在）的节点集。 如果不存在这样的节点，则返回空的节点集合。

如果第一个参数节点的类型为“`leafref`”，则该函数将返回一个包含`leafref`引用的节点的节点集。 具体来说，这个集合包含由`leafref`的“`path`”语句（[第9.9.2节](../section-9/9.2.md#992-规范形式)）选择的节点，它们与第一个参数节点具有相同的值。

如果第一个参数节点是任何其他类型，则返回空节点集。

#### 10.3.1.1. 使用示例

```YANG
list interface {
  key "name type";
  leaf name { ... }
  leaf type { ... }
  leaf enabled {
    type boolean;
  }
  ...
}

container mgmt-interface {
  leaf name {
    type leafref {
      path "/interface/name";
    }
  }
  leaf type {
    type leafref {
      path "/interface[name=current()/../name]/type";
    }
    must 'deref(.)/../enabled = "true"' {
      error-message
        "The management interface cannot be disabled.";
    }
  }
}
```

## 10.4. `YANG`类型的“`identityref`”函数

### 10.4.1. `derived-from()`

```XPath
boolean derived-from(node-set nodes, string identity)
```

如果参数“`nodes`”中的任何节点是“`identityref`”类型的节点，并且其值是从（参见[第7.18.2节](../section-7/7.18.md#7182-base声明)）派生的标识，则`derived-from()`函数返回“`true`”; 否则，返回“`false`”。

参数“`identity`”是与[第14节](../section-14/README.md)中的“`identifier-ref`”规则相匹配的字符串。如果前缀存在于标识中，则它指的是在导入了该前缀的模块中定义的标识，如果前缀与本地模块的前缀匹配，那么该标识将在该模块中定义。 如果不存在前缀，则标识是指在当前模块或包含的子模块中定义的标识。

#### 10.4.1.1. 使用示例

```YANG
module example-interface {
  yang-version 1.1;

  ...
  identity interface-type;

  identity ethernet {
    base interface-type;
  }

  identity fast-ethernet {
    base ethernet;
  }

  identity gigabit-ethernet {
    base ethernet;
  }

  list interface {
    key name;
    ...
    leaf type {
      type identityref {
        base interface-type;
      }
    }
    ...
  }

  augment "/interface" {
    when 'derived-from(type, "exif:ethernet")';
    // generic Ethernet definitions here
  }
  ...
}
```

### 10.4.2. `derived-from-or-self()`

```XPath
boolean derived-from-or-self(node-set nodes, string identity)
```

如果参数“`nodes`”中的任何节点是“`identityref`”类型的节点，并且其值是等于或来源于其的标识，则`derived-from-or-self()`函数将返回“`true`”（请参阅[第7.18.2节](../section-7/7.18.md#7182-base声明)）身份“`identity`”; 否则，返回“`false`”。

参数“`identity`”是与[第14节](../section-14/README.md)中的“`identifier-ref`”规则相匹配的字符串。如果前缀存在于标识中，则它指的是在导入了该前缀的模块中定义的标识，如果前缀与本地模块的前缀匹配，那么该标识将在该模块中定义。 如果不存在前缀，则标识是指在当前模块或包含的子模块中定义的标识。

#### 使用示例

[第10.4.1.1节](README.md#10411-使用示例)定义的模块也可能有：

```YANG
augment "/interface" {
  when 'derived-from-or-self(type, "exif:fast-ethernet");
  // Fast-Ethernet-specific definitions here
}
```

## 10.5. `YANG`类型“`enumeration`”函数

### 10.5.1. `enum-value()`

```XPath
number enum-value(node-set nodes)
```

`enum-value()`函数检查参数“`nodes`”中文档顺序中的第一个节点是否为“`enumeration`”类型的节点，并返回枚举的整数值。 如果“`nodes`”节点集为空，或者“`nodes`”中的第一个节点不是“`enumeration`”类型，则返回`NaN`（不是数字）。

#### 10.5.1.1. 使用示例

有了这个数据模型：

```YANG
list alarm {
  ...
  leaf severity {
    type enumeration {
      enum cleared {
        value 1;
      }
      enum indeterminate {
        value 2;
      }
      enum minor {
        value 3;
      }
      enum warning {
        value 4;
      }
      enum major {
        value 5;
      }
      enum critical {
        value 6;
      }
    }
  }
}
```

以下`XPath`表达式仅选择严重性为“`major`”或更高的警报：

```XPath
/alarm[enum-value(severity) >= 5]
```

## 10.6. `YANG`类型的“`bits`”函数

### 10.6.1. `bit-is-set()`

```XPath
boolean bit-is-set(node-set nodes, string bit-name)
```

如果参数“`nodes`”中的文档顺序中的第一个节点是“`bits`”类型的节点，并且其值设置了“`bit-name`”位，则`bit-is-set()`函数返回“`true`” 否则，返回“`false`”。

#### 10.6.1.1. 使用示例

如果一个接口有这个叶子：

```YANG
leaf flags {
  type bits {
    bit UP;
    bit PROMISCUOUS
    bit DISABLED;
  }
 }
```

可以使用以下`XPath`表达式来选择带有`UP`标志的所有接口：

```XPath
/interface[bit-is-set(flags, "UP")]
```
