---
title: "&lt;para&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<para>"
  - "para"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<para> (C#-XML-Tag)"
  - "para (C#-XML-Tag)"
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;para&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<para>content</para>  
```  
  
#### Parameter  
 `content`  
 Der Text des Absatzes.  
  
## Hinweise  
 Das \<para\>\-Tag ist für die Verwendung innerhalb eines Tags, wie [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md) oder [\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md), vorgesehen und ermöglicht die Strukturierung des Texts.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 Ein Beispiel für das Verwenden von \<para\> finden Sie unter [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)