---
title: "&lt;see&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "see XML tag"
  - "<see> XML tag"
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;see&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt einen Link zu einem anderen Member an.  
  
## Syntax  
  
```  
<see cref="member"/>  
```  
  
#### Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML\-Ausgabe.  `member` muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
## Hinweise  
 Mit dem `<see>`\-Tag wird ein Link im Text angegeben.  Mit [\<seealso\>](../../../visual-basic/language-reference/xmldoc/seealso.md) wird Text angegeben, der in einem "Siehe auch"\-Abschnitt angezeigt werden soll.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel verweist das `<see>`\-Tag im `UpdateRecord`\-Hinweisabschnitt auf die `DoesRecordExist`\-Methode.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)