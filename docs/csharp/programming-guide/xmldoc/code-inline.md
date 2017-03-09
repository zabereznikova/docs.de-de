---
title: "&lt;c&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "c"
  - "<c>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<c> (C#-XML-Tag)"
  - "c (C#-XML-Tag)"
  - "Code, Markieren von Text als [C#]"
  - "Text, Markieren als Code [C#]"
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;c&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<c>text</c>  
```  
  
#### Parameter  
 `text`  
 der Text, der als Code angegeben werden soll.  
  
## Hinweise  
 Mit dem \<c\>\-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  Zum Angeben mehrerer Zeilen als Code wird [\<code\>](../../../csharp/programming-guide/xmldoc/code.md) verwendet.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/code-inline_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)