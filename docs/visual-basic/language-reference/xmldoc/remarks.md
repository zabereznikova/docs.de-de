---
title: "&lt;remarks&gt; (Visual Basic) | Microsoft Docs"
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
  - "<remarks> XML tag"
  - "remarks XML tag"
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;remarks&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt einen Hinweisabschnitt für den Member an.  
  
## Syntax  
  
```  
<remarks>description</remarks>  
```  
  
#### Parameter  
 `description`  
 eine Beschreibung des Members.  
  
## Hinweise  
 Verwenden Sie das `<remarks>`\-Tag, um Informationen über einen Typ hinzuzufügen und die mit [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md) angegebenen Informationen zu ergänzen.  
  
 Diese Informationen werden im Objektkatalog.  Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mit dem `<remarks>`\-Tag erläutert, was von der `UpdateRecord`\-Funktion zurückgegeben wird.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)