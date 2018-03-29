# 3. 术语

本文件中使用以下术语：

- 操作(`action`)：为数据树中的节点定义的操作。

- `anydata`：一个数据节点，用来包含一组可以由`YANG`建模的未知节点，不含`anyxml`。

- `anyxml`：一个数据节点，用来包含一个未知的`XML`数据块。

- 扩充(`augment`)：将新的节点添加到先前定义的节点中。

- 基本类型(`base type`)：派生类型用来继承的基础类型，可以是内置类型，也可以是其他派生类型。

- 内置类型(`built-in type`)：`YANG`语言定义的内置数据类型，如`uint32`或`string`。

- 选择(`choice`)：一个选择节点，一次操作中只能使用其中的一个分支。

- 客户端(`client`)：可以根据YANG模型定义通过某种网络管理协议来访问服务器数据的实体。

- 一致性(`conformance`)：衡量服务器遵循数据模型的准确程度。

- 容器(`container`)：树据树中最多只有一个实例的一个内部数据节点, 一个容器自身没有值，可以有多个子节点。

- 数据定义语句(`data definition statement`)：定义新数据节点的语句。 “`container`”，“`leaf`”，“`leaf-list`”，“`list`”，“`choice`”，“`case`”，“`augment`”，“`uses`”，“`anydata`”和“`anyxml`”中的一个。

- 数据模型(`data model`)：数据模型描述如何表示和访问数据。

- 数据节点(`data node`)：可以在数据树中实例化的节点。`container`，`leaf`，`leaf-list`，`list`，`anydata`和`anyxml`之一。

- 数据树(`data tree`)：用`YANG`建模的任何数据的实例化树，例如配置数据，状态数据，配置和状态的组合数据，`RPC`或`action`的输入数据，`RPC`或`action`的输出数据或通数据知。

- 派生类型(`derived type`)：派生自内置类型（如`uint32`）或其他派生类型的类型。

- 扩展(`extension`)：扩展将非`YANG`语义附加到语句中。 “`extension`”语句定义了新的语句来表达这些语义。

- 特性(`feature`)：用于将模型的一部分标记为可选的机制。将这部分模型定义绑定到一个特性名称标签上，并且只有在服务器支持该特性时才有效。

- 组定义(`grouping`)：节点定义宏，在使用处展开用以重用一组节点定义，可以在本模块中使用，也可以在import了本模型的其他模块中使用。 “`grouping`”语句自身不会在模型树中添加任何节点，只有在使用处才会展开节点定义。

- 标识符(`identifier`)：用于标识YANG模型中各种元素的字符串。

- 标识(`identity`)：一个全局的，抽象的，无类型的名字。

- 实例标识符(`instance identifier`)：用于标识数据树中的特定节点的机制。

- 内部节点(`interior node`)：层次结构树中不是叶节点的节点。

- 叶节点(`leaf`)：数据树中至多存在一个实例的数据节点。叶子有一个值，但没有子节点。

- 叶列表(`leaf-list`)：与叶节点类似，但定义了一组唯一可识别的节点，而不是单个节点。每个节点都有一个值，但没有子节点。

- 列表(`list`)：数据树中可能存在多个实例的内部节点。一个列表有一组子节点，但没有值。

- 必选节点(`mandatory node`)：必选节点是以下之一：

  - “`mandatory`”属性为“`true`”的`leaf`，`choice`，`anydata`或`anyxml`节点。
  - “`min-elements`”属性大于零值的列表(`list`)或叶列表(`leaf-list`)节点。
  - 没有“`presence`”语句的容器(`container`)节点，并且至少有一个子节点为必选节点。

- 模块(`module`)：`YANG`模块用来定义层次化的节点。通过其定义和从其他地方导入或包含的定义，模块是自包含的和“可编译的”。

- 非刷单容器(`non-presence container`)：是否存在本身没有意义的container，仅用于包含子节点，如果没有子节点则其本身是否存在无意义。

- 刷单容器(`presence container`)：是否存在本身就具有意义的container。

- `RPC`：远程过程调用。

- RPC操作(`RPC operation`)：一次特定的远程过程调用。

- 模型节点(`schema node`)：模型树中的节点。 `action`，`container`，`leaf`，`leaf-list`，`list`，`choice`，`case`，`rpc`，`input`，`output`，`notification`，`anydata`和`anyxml`中的一个。

- 模型节点标识符(`schema node identifier`)：用于标识模式树中特定节点的机制。

- 模型树(`schema tree`)：模块中定义的层次化树。

- 服务器(`server`)：通过某种网络管理协议，根据YANG模型定义，为客户端提供数据访问的实体。

- 服务器偏差(`server deviation`)：服务器未能忠实地实现模块。

- 子模块(`submodule`)：部分模块定义，用于为模块提供组成部分，包含派生类型，分组，数据节点，`RPC`，操作和通知。一个`YANG`模块可以由多个子模块构成。

- 顶层数据节点(`top-level data node`)：一个数据节点，在这个节点和“模块”或“子模块”语句之间没有其他数据节点。

- 使用(`uses`)：“`uses`”语句用于在当前位置展开“组定义”宏，。展开时可以进行改进和扩展修饰以适应特定的需求。

- 值空间(`value space`)：对于数据类型;该数据类型允许的一组值。对于叶或叶列表实例;它的数据类型的值空间。

以下术语在[RFC6241](https://tools.ietf.org/html/rfc6241)中定义：

- 配置数据(`configuration data`)

- 配置数据仓库(`configuration datastore`)

- 数据仓库(`datastore`)

- 状态数据(`state data`)

当用`YANG`建模时，数据仓库被认为是一个实例化的数据树。

在使用`YANG`建模时，配置数据仓库被认为是由配置数据实例化的数据树。
