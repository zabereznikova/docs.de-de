---
title: "&lt;exception&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "exception"
  - "<exception>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<exception> (C#-XML-Tag)"
  - "exception (C#-XML-Tag)"
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# &lt;exception&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Parameter  
 cref \= "`member`"  
 ein Verweis auf eine Ausnahme, die in der aktuellen Kompilierungsumgebung verfügbar ist.  Der Compiler überprüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt `member` in den in der XML\-Ausgabe enthaltenen kanonischen Elementnamen.  `member` muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
 Weitere Informationen zum Erstellen von cref\-Verweisen auf einen generischen Typ finden Sie unter [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Eine Beschreibung der Ausnahme.  
  
## Hinweise  
 Mit dem \<exception\>\-Tag können Sie festlegen, welche Ausnahmen ausgelöst werden können.  Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer übernommen werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
 Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md).  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)