---
title: "&lt;c&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "c XML tag"
  - "<c> XML tag"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;c&gt; (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass es sich bei Text innerhalb einer Beschreibung um Code handelt.  
  
## Syntax  
  
```  
<c>text</c>  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`text`|der Text, der als Code angegeben werden soll.|  
  
## Hinweise  
 Mit dem `<c>`\-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  Verwenden Sie [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md), um mehrere Zeilen als Code anzugeben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mit dem `<c>`\-Tag im Zusammenfassungsabschnitt angegeben, dass es sich bei `Counter` um Code handelt.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)