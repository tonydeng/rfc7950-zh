# Summary

- [关于RFC7950中文翻译](README.md)
- [1. 介绍](section-1/README.md)
    - [1.1. Summary of Changes from RFC 6020](section-1/summary-of-changes-from-RFC-6020.md)
- [2. Key Words]()
- [3. Terminology]()
    - [3.1. A Note on Examples]()
- [4. YANG Overview]()
    - [4.1. Functional Overview]()
    - [4.2. Language Overview]()
    - [4.2.1. Modules and Submodules]()
    - [4.2.2. Data Modeling Basics]()
    - [4.2.3. Configuration and State Data]()
    - [4.2.4. Built-In Types]()
    - [4.2.5. Derived Types (typedef)]()
    - [4.2.6. Reusable Node Groups (grouping)]()
    - [4.2.7. Choices]()
    - [4.2.8. Extending Data Models (augment)]()
    - [4.2.9. Operation Definitions]()
    - [4.2.10. Notification Definitions]()
- [5. Language Concepts]()
    - [5.1. Modules and Submodules]()
        - [5.1.1. Import and Include by Revision]()
        - [5.1.2. Module Hierarchies]()
    - [5.2. File Layout]()
    - [5.3. XML Namespaces]()
        - [5.3.1. YANG XML Namespace]()
    - [5.4. Resolving Grouping, Type, and Identity Names]()
    - [5.5. Nested Typedefs and Groupings]()
    - [5.6. Conformance]()
        - [5.6.1. Basic Behavior]()
        - [5.6.2. Optional Features]()
        - [5.6.3. Deviations]()
        - [5.6.4. Announcing Conformance Information in NETCONF]()
        - [5.6.5. Implementing a Module]()
    - [5.7. Datastore Modification]()
- [6. YANG Syntax]()
    - [6.1. Lexical Tokenization]()
        - [6.1.1. Comments]()
        - [6.1.2. Tokens]()
        - [6.1.3. Quoting]()
    - [6.2. Identifiers]()
        - [6.2.1. Identifiers and Their Namespaces]()
    - [6.3. Statements]()
        - [6.3.1. Language Extensions]()
    - [6.4. XPath Evaluations]()
        - [6.4.1. XPath Context]()
    - [6.5. Schema Node Identifier]()
7. YANG Statements ................................................55
    7.1. The "module" Statement ....................................55
        7.1.1. The module's Substatements .........................56
        7.1.2. The "yang-version" Statement .......................57
        7.1.3. The "namespace" Statement ..........................57
        7.1.4. The "prefix" Statement .............................57
        7.1.5. The "import" Statement .............................58
        7.1.6. The "include" Statement ............................59
        7.1.7. The "organization" Statement .......................60
        7.1.8. The "contact" Statement ............................60
        7.1.9. The "revision" Statement ...........................60
        7.1.10. Usage Example .....................................61
    7.2. The "submodule" Statement .................................62
        7.2.1. The submodule's Substatements ......................63
        7.2.2. The "belongs-to" Statement .........................63
        7.2.3. Usage Example ......................................64
    7.3. The "typedef" Statement ...................................65
        7.3.1. The typedef's Substatements ........................65
        7.3.2. The typedef's "type" Statement .....................65
        7.3.3. The "units" Statement ..............................65
        7.3.4. The typedef's "default" Statement ..................66
        7.3.5. Usage Example ......................................66
    7.4. The "type" Statement ......................................66
        7.4.1. The type's Substatements ...........................67
    7.5. The "container" Statement .................................67
        7.5.1. Containers with Presence ...........................67
        7.5.2. The container's Substatements ......................68
        7.5.3. The "must" Statement ...............................69
        7.5.4. The must's Substatements ...........................70
        7.5.5. The "presence" Statement ...........................71
        7.5.6. The container's Child Node Statements ..............71
        7.5.7. XML Encoding Rules .................................71
        7.5.8. NETCONF <edit-config> Operations ...................72
        7.5.9. Usage Example ......................................72
    7.6. The "leaf" Statement ......................................73
        7.6.1. The leaf's Default Value ...........................74
        7.6.2. The leaf's Substatements ...........................75
        7.6.3. The leaf's "type" Statement ........................75
        7.6.4. The leaf's "default" Statement .....................75
        7.6.5. The leaf's "mandatory" Statement ...................76
        7.6.6. XML Encoding Rules .................................76
        7.6.7. NETCONF <edit-config> Operations ...................76
        7.6.8. Usage Example ......................................77
    7.7. The "leaf-list" Statement .................................77
        7.7.1. Ordering ...........................................78
        7.7.2. The leaf-list's Default Values .....................79
        7.7.3. The leaf-list's Substatements ......................80
        7.7.4. The leaf-list's "default" Statement ................80
        7.7.5. The "min-elements" Statement .......................80
        7.7.6. The "max-elements" Statement .......................81
        7.7.7. The "ordered-by" Statement .........................81
        7.7.8. XML Encoding Rules .................................82
        7.7.9. NETCONF <edit-config> Operations ...................82
        7.7.10. Usage Example .....................................83
        7.8. The "list" Statement ......................................84
        7.8.1. The list's Substatements ...........................85
        7.8.2. The list's "key" Statement .........................85
        7.8.3. The list's "unique" Statement ......................86
        7.8.4. The list's Child Node Statements ...................87
        7.8.5. XML Encoding Rules .................................88
        7.8.6. NETCONF <edit-config> Operations ...................88
        7.8.7. Usage Example ......................................90
        7.9. The "choice" Statement ....................................93
        7.9.1. The choice's Substatements .........................94
        7.9.2. The choice's "case" Statement ......................94
        7.9.3. The choice's "default" Statement ...................96
        7.9.4. The choice's "mandatory" Statement .................98
        7.9.5. XML Encoding Rules .................................98
        7.9.6. Usage Example ......................................99
        7.10. The "anydata" Statement .................................100
        7.10.1. The anydata's Substatements ......................100
        7.10.2. XML Encoding Rules ...............................101
        7.10.3. NETCONF <edit-config> Operations .................101
        7.10.4. Usage Example ....................................101
        7.11. The "anyxml" Statement ..................................102
        7.11.1. The anyxml's Substatements .......................103
        7.11.2. XML Encoding Rules ...............................103
        7.11.3. NETCONF <edit-config> Operations .................103
        7.11.4. Usage Example ....................................104
        7.12. The "grouping" Statement ................................104
        7.12.1. The grouping's Substatements .....................105
        7.12.2. Usage Example ....................................105
        7.13. The "uses" Statement ....................................106
        7.13.1. The uses's Substatements .........................106
        7.13.2. The "refine" Statement ...........................106
        7.13.3. XML Encoding Rules ...............................107
        7.13.4. Usage Example ....................................107
        7.14. The "rpc" Statement .....................................108
        7.14.1. The rpc's Substatements ..........................109
        7.14.2. The "input" Statement ............................109
        7.14.3. The "output" Statement ...........................110
        7.14.4. NETCONF XML Encoding Rules .......................111
        7.14.5. Usage Example ....................................112
        7.15. The "action" Statement ..................................113
             7.15.1. The action's Substatements .......................114
             7.15.2. NETCONF XML Encoding Rules .......................114
             7.15.3. Usage Example ....................................115
        7.16. The "notification" Statement ............................116
             7.16.1. The notification's Substatements .................117
             7.16.2. NETCONF XML Encoding Rules .......................117
             7.16.3. Usage Example ....................................118
        7.17. The "augment" Statement .................................119
             7.17.1. The augment's Substatements ......................121
             7.17.2. XML Encoding Rules ...............................121
             7.17.3. Usage Example ....................................122
        7.18. The "identity" Statement ................................124
             7.18.1. The identity's Substatements .....................124
             7.18.2. The "base" Statement .............................124
             7.18.3. Usage Example ....................................125
        7.19. The "extension" Statement ...............................126
             7.19.1. The extension's Substatements ....................126
             7.19.2. The "argument" Statement .........................127
             7.19.3. Usage Example ....................................127
        7.20. Conformance-Related Statements ..........................128
             7.20.1. The "feature" Statement ..........................128
             7.20.2. The "if-feature" Statement .......................130
             7.20.3. The "deviation" Statement ........................131
        7.21. Common Statements .......................................134
             7.21.1. The "config" Statement ...........................134
             7.21.2. The "status" Statement ...........................135
             7.21.3. The "description" Statement ......................136
             7.21.4. The "reference" Statement ........................136
             7.21.5. The "when" Statement .............................136
        8. Constraints ...................................................138
            8.1. Constraints on Data ......................................138
            8.2. Configuration Data Modifications .........................139
            8.3. NETCONF Constraint Enforcement Model .....................139
                 8.3.1. Payload Parsing ...................................139
                 8.3.2. NETCONF <edit-config> Processing ..................140
                 8.3.3. Validation ........................................141
        9. Built-In Types ................................................141
            9.1. Canonical Representation .................................141
            9.2. The Integer Built-In Types ...............................142
                 9.2.1. Lexical Representation ............................142
                 9.2.2. Canonical Form ....................................143
                 9.2.3. Restrictions ......................................143
                 9.2.4. The "range" Statement .............................143
                 9.2.5. Usage Example .....................................144
         9.3. The decimal64 Built-In Type ..............................144
              9.3.1. Lexical Representation ............................145
              9.3.2. Canonical Form ....................................145
              9.3.3. Restrictions ......................................145
              9.3.4. The "fraction-digits" Statement ...................145
              9.3.5. Usage Example .....................................146
         9.4. The string Built-In Type .................................146
              9.4.1. Lexical Representation ............................146
              9.4.2. Canonical Form ....................................147
              9.4.3. Restrictions ......................................147
              9.4.4. The "length" Statement ............................147
              9.4.5. The "pattern" Statement ...........................148
              9.4.6. The "modifier" Statement ..........................148
              9.4.7. Usage Example .....................................149
         9.5. The boolean Built-In Type ................................150
              9.5.1. Lexical Representation ............................150
              9.5.2. Canonical Form ....................................150
              9.5.3. Restrictions ......................................150
         9.6. The enumeration Built-In Type ............................150
              9.6.1. Lexical Representation ............................150
              9.6.2. Canonical Form ....................................151
              9.6.3. Restrictions ......................................151
              9.6.4. The "enum" Statement ..............................151
              9.6.5. Usage Example .....................................152
         9.7. The bits Built-In Type ...................................154
              9.7.1. Restrictions ......................................154
              9.7.2. Lexical Representation ............................154
              9.7.3. Canonical Form ....................................154
              9.7.4. The "bit" Statement ...............................155
              9.7.5. Usage Example .....................................156
         9.8. The binary Built-In Type .................................157
              9.8.1. Restrictions ......................................157
              9.8.2. Lexical Representation ............................157
              9.8.3. Canonical Form ....................................157
         9.9. The leafref Built-In Type ................................157
              9.9.1. Restrictions ......................................158
              9.9.2. The "path" Statement ..............................158
              9.9.3. The "require-instance" Statement ..................159
              9.9.4. Lexical Representation ............................159
              9.9.5. Canonical Form ....................................159
              9.9.6. Usage Example .....................................159
         9.10. The identityref Built-In Type ...........................163
              9.10.1. Restrictions .....................................163
              9.10.2. The identityref's "base" Statement ...............163
              9.10.3. Lexical Representation ...........................163
              9.10.4. Canonical Form ...................................164
              9.10.5. Usage Example ....................................164
              9.11. The empty Built-In Type .................................165
                 9.11.1. Restrictions .....................................165
                 9.11.2. Lexical Representation ...........................165
                 9.11.3. Canonical Form ...................................165
                 9.11.4. Usage Example ....................................166
            9.12. The union Built-In Type .................................166
                 9.12.1. Restrictions .....................................166
                 9.12.2. Lexical Representation ...........................166
                 9.12.3. Canonical Form ...................................167
                 9.12.4. Usage Example ....................................167
            9.13. The instance-identifier Built-In Type ...................168
                 9.13.1. Restrictions .....................................168
                 9.13.2. Lexical Representation ...........................169
                 9.13.3. Canonical Form ...................................169
                 9.13.4. Usage Example ....................................169
            10. XPath Functions ..............................................170
                10.1. Function for Node Sets ..................................170
                     10.1.1. current() ........................................170
                10.2. Function for Strings ....................................170
                     10.2.1. re-match() .......................................170
                10.3. Function for the YANG Types "leafref" and
                      "instance-identifier" ...................................171
                     10.3.1. deref() ..........................................171
                10.4. Functions for the YANG Type "identityref" ...............172
                     10.4.1. derived-from() ...................................172
                     10.4.2. derived-from-or-self() ...........................174
                10.5. Function for the YANG Type "enumeration" ................174
                     10.5.1. enum-value() .....................................174
                10.6. Function for the YANG Type "bits" .......................175
                     10.6.1. bit-is-set() .....................................175
            11. Updating a Module ............................................176
            12. Coexistence with YANG Version 1 ..............................179
            13. YIN ..........................................................179
                13.1. Formal YIN Definition ...................................180
                     13.1.1. Usage Example ....................................182
            14. YANG ABNF Grammar ............................................184
            15. NETCONF Error Responses for YANG-Related Errors ..............211
                15.1. Error Message for Data That Violates a "unique"
                      Statement ...............................................211
                15.2. Error Message for Data That Violates a
                      "max-elements" Statement ................................211
                15.3. Error Message for Data That Violates a
                      "min-elements" Statement ................................211
                15.4. Error Message for Data That Violates a "must"
                      Statement ...............................................212
                15.5. Error Message for Data That Violates a
                      "require-instance" Statement ............................212

                15.6. Error Message for Data That Violates a Mandatory
      "choice" Statement ......................................212
                15.7. Error Message for the "insert" Operation ................212
16. IANA Considerations ..........................................213
17. Security Considerations ......................................213
18. References ...................................................214
18.1. Normative References ....................................214
18.2. Informative References ..................................215
Acknowledgements .................................................217
Contributors .....................................................217
Author's Address .................................................217
