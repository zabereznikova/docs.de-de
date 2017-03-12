---
title: "&lt;remarks&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> (C#-XML-Tag)"
  - "remarks (C#-XML-Tag)"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;remarks&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<remarks>description</remarks>  
```  
  
#### Parameter  
 `Description`  
 eine Beschreibung des Members.  
  
## Hinweise  
 Mittels des \<remarks\>\-Tags werden Informationen über einen Typ hinzugefügt. Diese dienen als Ergänzung zu den mit [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) angegebenen Informationen.  Diese Informationen werden im [Object Browser Window](http://msdn.microsoft.com/de-de/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/remarks_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)