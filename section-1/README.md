# 1. 介绍

`YANG`是一种数据建模语言，最初设计用于模拟由网络配置协议（`NETCONF`），`NETCONF`远程过程调用和NETCONF通知[RFC6241](https://tools.ietf.org/html/rfc6241)操作的配置和状态数据。自从`YANG`版本1 [RFC6020](https://tools.ietf.org/html/rfc6240)发布以来，`YANG`已被用于或被提议用于其他协议（例如，[RESTCONF](https://tools.ietf.org/html/rfc7950#ref-RESTCONF)和约束应用协议（`CoAP`）管理接口[CoMI](https://tools.ietf.org/html/rfc7950#ref-CoMI)）。此外，已经提出了不同于`XML`的编码（例如，`JSON` [RFC7951](https://tools.ietf.org/html/rfc7951)）。

本文档描述了`YANG`语言版本1.1的语法和语义。它还描述了如何在可扩展标记语言（XML）[XML](https://tools.ietf.org/html/rfc7950#ref-XML)中对`YANG`模块中定义的数据模型进行编码，以及如何使用`NETCONF`操作来操作数据。其他协议和编码也是可能的，但不在本规范的范围之内。

在开发`YANG`数据模型方面，[YANG-Guidelines](https://tools.ietf.org/html/rfc7950#ref-YANG-Guidelines)提供了一些指导和建议。

请注意，[RFC 6020](https://tools.ietf.org/html/rfc6020)这个文件不会被废弃。
