# 3. 术语

本文件中使用以下术语：

- 操作(`action`)：为数据树中的节点定义的操作。

- `anydata`：一个数据节点，可以包含一个未知的节点集合，除了`anyxml`以外，可以由`YANG`建模。

- `anyxml`：一个数据节点，可以包含一个未知的`XML`数据块。

- 扩充(`augment`)：将新的模式节点添加到先前定义的模式节点。

- 基本类型(`base type`)：衍生派生类型的类型，可以是内置类型，也可以是其他派生类型。

- 内置类型(`built-in type`)：`YANG`语言定义的`YANG`数据类型，如`uint32`或`string`。

- 选择(`choice`)：一个模式节点，其中只有一种标识的可选方案是有效的。

- 客户端(`client`)：通过某种网络管理协议，可以访问服务器上YANG定义数据的实体。

- 一致性(`conformance`)：衡量服务器遵循数据模型的准确程度。

- 容器(`container`)：一个内部数据节点，它存在于数据树的大多数实例中。 一个容器只有子节点，没有值。

- 数据定义语句(`data definition statement`)：定义新数据节点的语句。 “`container`”，“`leaf`”，“`leaf-list`”，“`list`”，“`choice`”，“`case`”，“`augment`”，“`uses`”，“`anydata`”和“`anyxml`”中的一个。

- 数据模型(`data model`)：数据模型描述如何表示和访问数据。

- 数据节点(`data node`)：模式树中可以在数据树中实例化的节点。`container`，`leaf`，`leaf-list`，`list`，`anydata`和`anyxml`之一。

- 数据树(`data tree`)：用`YANG`建模的任何数据的实例化树，例如配置数据，状态数据，组合配置和状态数据，`RPC`或操作输入，`RPC`或操作输出或通知。

- 派生类型(`derived type`)：派生自内建类型（如`uint32`）或其他派生类型的类型。

- 扩展(`extension`)：扩展将非`YANG`语义附加到语句中。 “`extension`”语句定义了新的语句来表达这些语义。

- 特征(`feature`)：用于将模型的一部分标记为可选的机制。定义可以使用功能名称进行标记，并仅在支持该功能的服务器上有效。

- 分组(`grouping`)：一组可重复使用的模式节点，可以在模块中本地使用，也可以从其他模块中使用。 “`grouping`”语句不是数据定义语句，因此不会在模式树中定义任何节点。

- 标识符(`identifier`)：用于按名称标识不同种类YANG项目的字符串。

- 身份(`identity`)：一个全球唯一的，抽象的，无类型的名字。

- 实例标识符(`instance identifier`)：用于标识数据树中的特定节点的机制。

- 内部节点(`interior node`)：层次结构内不是叶节点的节点。

- 叶节点(`leaf`)：数据树中至多存在一个实例的数据节点。叶子有一个值，但没有子节点。

- 叶列表(`leaf-list`)：与叶节点类似，但定义了一组唯一可识别的节点，而不是单个节点。每个节点都有一个值，但没有子节点。

- 列表(`list`)：数据树中可能存在多个实例的内部数据节点。一个列表没有任何价值，而是一组子节点。

- 强制节点(`mandatory node`)：强制节点是以下之一：

    - 带有值为“`true`”的“`mandatory`”语句的`leaf`，`choice`，`anydata`或`anyxml`节点。
    - 带有大于零值的“`min-elements`”语句的列表或叶列表节点。
    - 没有“`presence`”语句的容器节点，并且至少有一个强制节点作为子节点。

- 模块(`module`)：`YANG`模块定义模式节点的层次结构。通过其定义和从其他地方导入或包含的定义，模块是自包含的和“可编译的”。

- 不存在容器(`non-presence container`)：一个没有其自身意义的容器，仅存在于包含子节点的容器中。

- 存在容器(`presence container`)：存在容器的容器本身具有某种意义。

- `RPC`：远程过程调用。

- RPC操作(`RPC operation`)：特定的远程过程调用。

- 模式节点(`schema node`)：模式树中的节点。 `action`，`container`，`leaf`，`leaf-list`，`list`，`choice`，`case`，`rpc`，`input`，`output`，`notification`，`anydata`和`anyxml`中的一个。

- 模式节点标识符(`schema node identifier`)：用于标识模式树中特定节点的机制。

- 模式树(`schema tree`)：模块中指定的定义层次结构。

- 服务器(`server`)：通过某种网络管理协议，提供对客户端访问YANG定义数据的实体。

- 服务器偏差(`server deviation`)：服务器忠实地执行模块的失败。

- 子模块(`submodule`)：部分模块定义，用于为模块提供派生类型，分组，数据节点，`RPC`，操作和通知。一个`YANG`模块可以由多个子模块构成。

- 顶层数据节点(`top-level data node`)：一个数据节点，在这个节点和“模块”或“子模块”语句之间没有其他数据节点。

- 使用(`uses`)：“`uses`”语句用于实例化“分组”语句中定义的一组模式节点。实例化的节点可以被改进和增加以适应任何特定的需求。

- 值空间(`value space`)：对于数据类型;数据类型允许的一组值。对于叶或叶列表实例;它的数据类型的值空间。

以下术语在[RFC6241](https://tools.ietf.org/html/rfc6241)中定义：

- 配置数据(`configuration data`)

- 配置数据存储(`configuration datastore`)

- 数据存储(`datastore`)

- 状态数据(`state data`)

当用`YANG`建模时，数据存储被实现为一个实例化的数据树。

在使用`YANG`建模时，配置数据存储实现为具有配置数据的实例化数据树。
