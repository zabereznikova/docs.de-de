---
title: "&lt;returns&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "returns"
  - "<returns>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<returns> (C#-XML-Tag)"
  - "returns (C#-XML-Tag)"
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;returns&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<returns>description</returns>  
```  
  
#### Parameter  
 `description`  
 Eine Beschreibung des Rückgabewerts.  
  
## Hinweise  
 Das \<returns\>\-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um den Rückgabewert zu beschreiben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#10](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/returns_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)