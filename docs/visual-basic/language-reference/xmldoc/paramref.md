---
title: "&lt;paramref&gt; (Visual Basic) | Microsoft Docs"
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
  - "paramref XML tag"
  - "<paramref> XML tag"
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;paramref&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Formatiert ein Wort als Parameter.  
  
## Syntax  
  
```  
<paramref name="name"/>  
```  
  
#### Parameter  
 `name`  
 der Name des Parameters, auf den verwiesen werden soll.  Der Name muss in doppelte Anführungszeichen \(**" "**\) eingeschlossen werden.  
  
## Hinweise  
 Mit dem `<paramref>`\-Tag können Sie angeben, dass es sich bei einem Wort um einen Parameter handelt.  Die XML\-Datei kann verarbeitet werden, um den Parameter in besonderer Weise zu formatieren.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mit dem `<paramref>`\-Tag auf den `id`\-Parameter verwiesen.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)