# 1. 介绍

`YANG`是一种数据建模语言，最初设计用于网络配置协议（`NETCONF`）的建模，包括配置数据,状态数据, `NETCONF`远程过程调用和NETCONF通知[RFC6241](https://tools.ietf.org/html/rfc6241)操作的配置和状态数据。自从`YANG`版本1 [RFC6020](https://tools.ietf.org/html/rfc6240)发布以来，`YANG`已被用于或被提议用于其他协议（例如，[RESTCONF](https://tools.ietf.org/html/rfc7950#ref-RESTCONF)以及CoAP的的[CoMI](https://tools.ietf.org/html/rfc7950#ref-CoMI)（`Constrained Application Protocol Management Interface`））。此外，已经提出了`XML`之外的编码（例如，`JSON` [RFC7951](https://tools.ietf.org/html/rfc7951)）。

本文档描述了`YANG`语言版本1.1的语法和语义。它还描述了如何使用XML[XML](https://tools.ietf.org/html/rfc7950#ref-XML)编码`YANG`模块中定义的数据模型，以及如何通过`NETCONF`协议来操作这些数据。其他协议和编码也是可能的，但超出了本规范的范围。

在开发`YANG`数据模型方面，[YANG-Guidelines](https://tools.ietf.org/html/rfc7950#ref-YANG-Guidelines)提供了一些指导和建议。

请注意，本RFC并不废弃[RFC 6020](https://tools.ietf.org/html/rfc6020)。
