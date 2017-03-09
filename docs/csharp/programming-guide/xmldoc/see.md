---
title: "&lt;see&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<see>"
  - "see"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<see> (C#-XML-Tag)"
  - "cref [C#], <see>-Tag"
  - "Querverweise [C#]"
  - "see (C#-XML-Tag)"
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;see&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<see cref="member"/>  
```  
  
#### Parameter  
 cref \= " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML\-Ausgabe.*member* muss in doppelte Anführungszeichen \(" "\) gesetzt werden.  
  
## Hinweise  
 Mit dem \<see\>\-Tag kann ein Link im Text angegeben werden.  Verwenden Sie [\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Siehe auch\-Abschnitt eingefügt werden soll.  Verwenden Sie das [cref\-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
 Im folgenden Beispiel wird ein \<see\>\-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.  
  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/see_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)