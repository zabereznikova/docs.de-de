---
title: "&lt;typeparam&gt; (Visual Basic) | Microsoft Docs"
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
  - "typeparam XML tag"
  - "<typeparam> XML tag"
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;typeparam&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Definiert einen Typparameternamen und eine Beschreibung.  
  
## Syntax  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Parameter  
 `name`  
 Der Name des Typparameters.  Der Name muss in doppelte Anführungszeichen \(**" "**\) eingeschlossen werden.  
  
 `description`  
 Eine Beschreibung des Typparameters.  
  
## Hinweise  
 Verwenden Sie das `<typeparam>`\-Tag im Kommentar für eine generische Typ\- oder Memberdeklaration, um einen der Typparameter zu beschreiben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird das `<typeparam>`\-Tag verwendet, um den `id`\-Parameter zu beschreiben.  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)