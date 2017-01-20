---
title: "&lt;returns&gt; (Visual Basic) | Microsoft Docs"
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
  - "returns XML tag"
  - "<returns> XML tag"
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;returns&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt den Rückgabewert der Eigenschaft oder Funktion an.  
  
## Syntax  
  
```  
<returns>description</returns>  
```  
  
#### Parameter  
 `description`  
 Eine Beschreibung des Rückgabewerts.  
  
## Hinweise  
 Verwenden Sie das `<returns>`\-Tag im Kommentar für eine Methodendeklaration, um den Rückgabewert zu beschreiben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mit dem `<returns>`\-Tag erläutert, was von der `DoesRecordExist`\-Funktion zurückgegeben wird.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)