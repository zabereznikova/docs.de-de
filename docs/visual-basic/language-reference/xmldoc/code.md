---
title: "&lt;code&gt; (Visual Basic) | Microsoft Docs"
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
  - "code XML tag"
  - "<code> XML tag"
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;code&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass der Text mehrere Codezeilen umfasst.  
  
## Syntax  
  
```  
<code>content</code>  
```  
  
#### Parameter  
 `content`  
 Der Text, der als Code gekennzeichnet werden soll.  
  
## Hinweise  
 Verwenden Sie das `<code>`\-Tag, um mehrere Zeilen als Code anzugeben.  Mit [\<c\>](../../../visual-basic/language-reference/xmldoc/c.md) wird angegeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 Dieses Beispiel verwendet das \<code\>\-Tag, um Beispielcode für die Verwendung des `ID`\-Feldes einzufügen.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)