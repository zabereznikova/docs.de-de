---
title: "&lt;summary&gt; (Visual Basic) | Microsoft Docs"
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
  - "<summary> XML tag"
  - "summary XML tag"
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;summary&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt die Zusammenfassung des Members an.  
  
## Syntax  
  
```  
<summary>description</summary>  
```  
  
#### Parameter  
 `description`  
 eine Zusammenfassung des Objekts.  
  
## Hinweise  
 Verwenden Sie das `<summary>`\-Tag, um einen Typ oder einen Typmember zu beschreiben.  Mit [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) können Sie zusätzliche Informationen zu einer Typbeschreibung angeben.  
  
 Der Text für das `<summary>`\-Tag ist die einzige Informationsquelle zu Typ in IntelliSense und wird auch im Objektkatalog angezeigt.  Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird das `<summary>`\-Tag verwendet, um die `ResetCounter`\-Methode und `Counter`\-Eigenschaft zu beschreiben.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)