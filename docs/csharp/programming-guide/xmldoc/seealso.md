---
title: "&lt;seealso&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cref"
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<seealso> (C#-XML-Tag)"
  - "cref [C#]"
  - "cref [C#], Siehe auch"
  - "Querverweise [C#], Tags"
  - "seealso (C#-XML-Tag)"
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;seealso&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<seealso cref="member"/>  
```  
  
#### Parameter  
 cref \= "`member`"  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen im Ausgabe\-XML. `member` muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
 Informationen für das Erstellen von cref\-Verweisen auf einen generischen Typ finden Sie unter [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
## Hinweise  
 Mit dem \<seealso\>\-Tag kann der Text, der möglicherweise in einem "Siehe auch"\-Abschnitt angezeigt werden soll, angegeben werden.  Mit [\<see\>](../../../csharp/programming-guide/xmldoc/see.md) wird ein Link im Text angegeben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 Ein Beispiel für das Verwenden von \<seealso\> finden Sie unter [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)