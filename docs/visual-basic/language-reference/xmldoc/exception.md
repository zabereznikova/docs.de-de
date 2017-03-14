---
title: "&lt;exception&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "<exception> XML tag"
  - "exception XML tag"
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;exception&gt; (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, welche Ausnahmen ausgelöst werden können.  
  
## Syntax  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Parameter  
 `member`  
 ein Verweis auf eine Ausnahme, die in der aktuellen Kompilierungsumgebung verfügbar ist.  Der Compiler überprüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt `member` in den in der XML\-Ausgabe enthaltenen kanonischen Elementnamen.  `member` muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
 `description`  
 eine Beschreibung.  
  
## Hinweise  
 Geben Sie mit dem `<exception>`\-Tag an, welche Ausnahmen ausgelöst werden können.  Dieses Tag wird auf eine Methodendefinition angewendet.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mit dem `<exception>`\-Tag eine Ausnahme beschrieben, die von der `IntDivide`\-Funktion ausgelöst werden kann.  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)